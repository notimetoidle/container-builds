FROM caddy:2.9-builder AS builder

RUN xcaddy build \
  --with github.com/lucaslorentz/caddy-docker-proxy/v2 \
  --with github.com/caddy-dns/cloudflare

FROM caddy:2.9

COPY --from=builder /usr/bin/caddy /usr/bin/caddy

CMD ["caddy", "run"]
