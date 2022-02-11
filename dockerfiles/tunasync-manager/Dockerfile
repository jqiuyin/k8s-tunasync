FROM ubuntu
RUN mkdir /tunasync
WORKDIR /tunasync
ADD https://github.com/tuna/tunasync/releases/latest/download/tunasync-linux-amd64-bin.tar.gz ./
RUN tar -xzf tunasync-linux-amd64-bin.tar.gz && rm tunasync-linux-amd64-bin.tar.gz
ENV TUNAPATH=/tunasync
ENV PATH=$PATH:$TUNAPATH
RUN mkdir /tunasync/config
COPY manager.conf ./config
VOLUME /tunasync/db
VOLUME /tunasync/config
ENTRYPOINT ["tunasync","manager","--config"]
CMD ["config/manager.conf"]