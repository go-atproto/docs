# Usage

```go
package main

import (
	"context"
	"fmt"

	"github.com/go-atproto/atproto"
)

func main() {
	c := atproto.New() // defaults to https://public.api.bsky.app

	feed, err := c.AuthorFeed(context.Background(), "bsky.app", 25, "")
	if err != nil {
		panic(err)
	}
	for _, p := range feed.Posts {
		fmt.Printf("@%s (%d likes): %s\n", p.Author.Handle, p.LikeCount, p.Text)
	}
}
```

Pass `feed.Cursor` back to `AuthorFeed` to page. `SearchPosts` works the same way anonymously. The authenticated `Timeline` needs a token: point the client at a PDS with `WithService("https://bsky.social")` and call `Login` first.

For the complete, always-current API — every type and field — see
[pkg.go.dev/github.com/go-atproto/atproto](https://pkg.go.dev/github.com/go-atproto/atproto).
