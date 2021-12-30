FROM alpine:3.15.0

WORKDIR /home
RUN wget "https://github.com/golang/mock/releases/download/v1.6.0/mock_1.6.0_linux_amd64.tar.gz" && \
    tar -xzf mock_1.6.0_linux_amd64.tar.gz && \
    rm mock_1.6.0_linux_amd64.tar.gz && \
    mv mock_1.6.0_linux_amd64/mockgen /usr/local/bin/mockgen
