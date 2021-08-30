FROM debian:stretch-slim

RUN apt-get update && \
    apt-get upgrade && \
    apt-get install -y build-essential libffi-dev git pkg-config vim python python3 && \
    rm -rf /var/lib/apt/lists/* && \
    git clone https://github.com/micropython/micropython.git && \
    cd micropython && \
    git submodule update --init && \
    cd mpy-cross && \
    make && \
    cd .. && \
    cd ports/unix && \
    make axtls && \
    make && \
    make install && \
    cd ../../.. && \
    rm -rf micropython
COPY ./install_packages.sh .
COPY ./requirements.txt .
RUN bash ./install_packages.sh && \
    rm -f install_packages.sh && \
    rm -f requirements.txt