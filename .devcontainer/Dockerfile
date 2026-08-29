FROM quay.io/jupyter/julia-notebook:julia-1.12.7

USER root
ENV DEBIAN_FRONTEND="noninteractive" TZ="UTC"

# ffmpeg: needed for CairoMakie's record()/mp4 export used in some lecture demos.
RUN apt-get update \
    && apt-get install -y --no-install-recommends git ffmpeg ca-certificates \
    && rm -rf /var/lib/apt/lists/*

USER ${NB_USER}
WORKDIR /home/${NB_USER}

# Install into the default (global) Julia environment rather than a
# project-local one, so students can `using X` in any notebook/REPL without
# first activating a project.
COPY Project.toml ${JULIA_PKGDIR}/environments/v1.12/

USER root
RUN chown ${NB_UID}:${NB_GID} ${JULIA_PKGDIR}/environments/v1.12/Project.toml
USER ${NB_USER}

ENV JULIA_NUM_THREADS="auto"
RUN set -eux; \
    arch="$(dpkg --print-architecture)"; \
    case "$arch" in \
        'amd64') \
            export JULIA_CPU_TARGET="generic;sandybridge,-xsaveopt,clone_all;haswell,-rdrnd,base(1);x86-64-v4,-rdrnd,base(1)"; \
            ;; \
        'arm64') \
            export JULIA_CPU_TARGET="generic;cortex-a57;thunderx2t99;carmel,clone_all;apple-m1,base(3);neoverse-512tvb,base(3)"; \
            ;; \
        *) \
            echo >&2 "error: current architecture ($arch) is not supported in this container"; \
            exit 1; \
            ;; \
    esac; \
    source /home/${NB_USER}/.profile && julia -e 'using Pkg; Pkg.resolve(); Pkg.instantiate(); Pkg.precompile()'

# Multi-user Docker setups sometimes leave the scratchspaces dir owned by the
# build-time UID; fix it up so a remapped container user can still write there.
USER root
RUN fix-permissions "${JULIA_PKGDIR}"
USER ${NB_USER}
