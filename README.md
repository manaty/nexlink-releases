# nexlink-releases

Installers for **Nexlink Desktop**, and the manifest the app reads to find them.

- Downloads: <https://github.com/manaty/nexlink-releases/releases/latest>
- Manifest: <https://raw.githubusercontent.com/manaty/nexlink-releases/main/desktop/latest.json>
- Releases: <https://github.com/manaty/nexlink-releases/releases>

This repository holds binaries only — no source. The source lives in a private
repository; a release here is produced from a `desktop-v*` tag there, and the
files are uploaded with `gh release upload`.

The layout the app depends on, and which must not change without a migration:

```
GET /desktop/latest.json      → { product, version, released_at, files: { <id>: { name, url, bytes, sha256 } } }
GET <file.url>                → the installer, immutable per version
```

`dl.nexlink.ph` is a GitHub Pages site on this repository (`CNAME` file); the
binaries are release assets, because Pages refuses files over 100 MB and the
installers are 96–124 MB. Nothing here is private and nothing needs a token.

Direct GitHub URLs are the supported download links while the custom domain certificate is being repaired.
