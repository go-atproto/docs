# API reference

Source-verified against [`go-atproto/atproto`](https://github.com/go-atproto/atproto). The
authoritative, versioned reference is
[pkg.go.dev/github.com/go-atproto/atproto](https://pkg.go.dev/github.com/go-atproto/atproto).

## Constructor & methods

| Symbol | Purpose |
|---|---|
| `New(...Option) *Client` | Construct a client; defaults to the public AppView. |
| `(*Client).AuthorFeed(ctx, actor, limit, cursor) (*Feed, error)` | An author's feed, anonymously via the public AppView. |
| `(*Client).SearchPosts(ctx, q, limit, cursor) (*Feed, error)` | Search posts. |
| `(*Client).Timeline(ctx, limit, cursor) (*Feed, error)` | Authenticated home timeline (requires `Login`). |
| `(*Client).Login(ctx, identifier, password) error` | Exchange credentials for an access token. |

## Options

Functional options passed to `New`:

| Option | Purpose |
|---|---|
| `WithService(url)` | Override the XRPC base URL / PDS. |
| `WithHTTPClient(*http.Client)` | Supply a custom HTTP client (timeouts, transport). |
| `WithUserAgent(ua)` | Set the `User-Agent` header. |

## Result types

| Type | Purpose |
|---|---|
| `Author` | A post's author (handle, display name, …). |
| `Image` | An image embed (`Fullsize`, `Alt`, …). |
| `Post` | A single post (`Text`, `LikeCount`, `Images`, …). |
| `Feed` | A page of posts plus a `Cursor` for pagination. |

!!! note
    This table is a map, not the contract. Field-level details live in the
    [package reference](https://pkg.go.dev/github.com/go-atproto/atproto) and the
    repository's `README`.
