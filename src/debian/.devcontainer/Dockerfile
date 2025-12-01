ARG VARIANT=trixie
FROM buildpack-deps:${VARIANT}-curl

### COPIED FROM UPSTREAM: https://github.com/devcontainers/images/blob/main/src/python/.devcontainer/Dockerfile ###
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    # Remove imagemagick due to https://security-tracker.debian.org/tracker/CVE-2019-10131
    && apt-get purge -y imagemagick imagemagick-6-common

RUN export DEBIAN_FRONTEND=noninteractive && curl -fsSL https://raw.githubusercontent.com/devcontainers/images/refs/heads/main/src/python/.devcontainer/scripts/install-subversion.sh \
    | bash

# Get Doppler and dotenvx installed
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y apt-transport-https ca-certificates curl gnupg \
    && curl -sLf --retry 3 --tlsv1.2 --proto "=https" 'https://packages.doppler.com/public/cli/gpg.DE2A7741A397C129.key' | gpg --dearmor -o /usr/share/keyrings/doppler-archive-keyring.gpg \
    && echo "deb [signed-by=/usr/share/keyrings/doppler-archive-keyring.gpg] https://packages.doppler.com/public/cli/deb/debian any-version main" | tee /etc/apt/sources.list.d/doppler-cli.list \
    && apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install doppler
RUN curl -sfS https://dotenvx.sh | sh