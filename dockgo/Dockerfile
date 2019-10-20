FROM docker:stable
RUN apk add --no-cache --virtual .build-deps bash gcc musl-dev openssl go &&\
    wget -O go.tgz https://dl.google.com/go/go1.13.3.src.tar.gz &&\
    tar -C /usr/local -xzf go.tgz &&\
    cd /usr/local/go/src/ &&\
    ./make.bash &&\
    apk del .build-deps
ENV PATH "/usr/local/go/bin:$PATH"
ENV GOPATH "/opt/go"
ENV PATH "$PATH:$GOPATH/bin"
