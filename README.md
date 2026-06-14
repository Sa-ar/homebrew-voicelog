# homebrew-voicelog

Homebrew tap for [voicelog](https://github.com/Sa-ar/voicelog) — the terminal-native primary surface for Voicelog.

## Install

```bash
brew install Sa-ar/voicelog/voicelog
```

Or via `go install`:

```bash
go install github.com/Sa-ar/voicelog/apps/cli/cmd/voicelog@latest
```

## How this tap stays current

This tap is updated automatically by [GoReleaser](https://goreleaser.com/) on every tagged release in the source repo:

1. Maintainer tags `vX.Y.Z` in `Sa-ar/voicelog`
2. `.github/workflows/release.yml` (source repo) runs GoReleaser
3. GoReleaser builds darwin/{amd64,arm64} + linux/{amd64,arm64} binaries
4. The `brews:` block in `apps/cli/.goreleaser.yaml` opens a PR here bumping `Formula/voicelog.rb` to the new version + checksum
5. Maintainer merges the PR → `brew install` resolves to the new release

## Manual install (if `brew install` ever breaks)

```bash
curl -L "https://github.com/Sa-ar/voicelog/releases/latest/download/voicelog_$(uname -s)_$(uname -m).tar.gz" | tar xz
sudo mv voicelog /usr/local/bin/
```

## Formula source

`Formula/voicelog.rb` is the auto-generated artifact. Don't edit by hand; let GoReleaser overwrite it on the next release.
