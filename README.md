# Block Panel pack mirror

Block Panel's resource pack, as the plugin builds it, for servers whose public address only carries
Minecraft (a proxy or a hosted SRV/port setup) and so can't serve the pack over HTTP themselves.

- `blockpanel.zip` - the latest build, for `resource-pack.mode: url`.
- `packs/<sha1>.zip` - each exact build, named by its SHA-1. Block Panel's third fallback link fills
  `{sha1}` into `resource-pack.fallback-url` and fetches the matching file, so the client's hash check
  passes.

The plugin can publish a build here by itself: set `resource-pack.fallback-repo` to this repo and
`resource-pack.fallback-token` to a fine-grained token with **Contents: read and write** on it. Without a
token, upload the server's `plugins/BlockPanel/pack/blockpanel.zip` here as `packs/<sha1>.zip` (the
hash is in the link `/blockpanel <sha1>.zip`).

Builds are deterministic (sorted entries, fixed timestamps), so the same plugin version and settings give
the same SHA-1 on any machine.
