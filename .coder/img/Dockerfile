# See our guides for writing custom images:
# https://coder.com/docs/guides/customization

FROM codercom/enterprise-base:ubuntu

USER root

# Add Teleport CLI (tsh, tctl)
RUN curl https://deb.releases.teleport.dev/teleport-pubkey.asc | sudo apt-key add - && \
    add-apt-repository 'deb https://deb.releases.teleport.dev/ stable main' && \
    apt-get update && \
    apt install teleport

# Add kubectl
RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && \
    chmod +x ./kubectl && \
    mv ./kubectl /usr/local/bin

USER coder