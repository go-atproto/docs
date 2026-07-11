# go-atproto

Pure-Go read client for Bluesky and the AT Protocol (XRPC).

A pure-Go, dependency-free read client for **Bluesky** and the **AT Protocol**, talking to the XRPC HTTP API. It targets the public Bluesky AppView at `https://public.api.bsky.app`, which serves read methods without authentication. An optional `Login` exchanges credentials for an access token to use authenticated methods such as the home timeline.

## Install

```sh
go get github.com/go-atproto/atproto
```

## At a glance

- **CGO-free** (`CGO_ENABLED=0`), Go 1.26+ — builds for every 64-bit target.
- **Zero third-party dependencies** — standard library only.
- **Read-only** — this is a read client; it does not post or mutate.
- BSD-3-Clause.

See [Usage](usage.md) for a runnable example and [API reference](api.md) for the
full surface. The canonical, always-current reference is
[pkg.go.dev](https://pkg.go.dev/github.com/go-atproto/atproto).
