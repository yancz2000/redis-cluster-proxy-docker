FROM alpine:3.12 AS compiler
RUN apk add git make gcc libc-dev linux-headers
RUN git clone https://github.com/RedisLabs/redis-cluster-proxy.git
RUN cd redis-cluster-proxy && make

FROM alpine:3.12
COPY --from=compiler /redis-cluster-proxy/src/redis-cluster-proxy /usr/local/bin/redis-cluster-proxy
ENTRYPOINT ["redis-cluster-proxy"]
