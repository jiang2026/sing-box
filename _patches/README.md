# Local patches

## sing (`./sing`)

Based on `github.com/sagernet/sing@v0.9.0-beta.4`.

Patch: SOCKS5 UDP ASSOCIATE — when the server advertises `0.0.0.0` / `::` / loopback
as the UDP relay (`BND.ADDR`), rewrite to the TCP peer IP + advertised port.
Without this, Android/client UDP through SOCKS (proxy UDP probe) fails when the
server listens on `0.0.0.0`.

Wired via `go.mod`:
`replace github.com/sagernet/sing => ./_patches/sing`
