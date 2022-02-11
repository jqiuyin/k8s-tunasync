FROM ubuntu
RUN mkdir /tunasync
WORKDIR /tunasync
ADD https://github.com/tuna/tunasync/releases/latest/download/tunasync-linux-amd64-bin.tar.gz ./
RUN tar -xzf tunasync-linux-amd64-bin.tar.gz && rm tunasync-linux-amd64-bin.tar.gz
ENV TUNAPATH=/tunasync
ENV PATH=$PATH:$TUNAPATH
RUN mkdir /tunasync/config
COPY worker.conf ./config
VOLUME /tunasync/mirror
VOLUME /tunasync/log
VOLUME /tunasync/config
ENTRYPOINT ["tunasync","worker","--config"]
CMD ["config/worker.conf"]