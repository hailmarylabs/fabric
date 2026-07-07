# HailMary Fabric

Make coding agents sharper by indexing your codebase and selecting only the context relevant to each task.

Fabric is an experimental local tool for Claude Code. It indexes your repo, preselects task-relevant files, and injects that context through a local loopback proxy.

## Install

Requirements:

- macOS Apple Silicon
- Claude Code installed

Works with Claude Code whether it is using the Anthropic API or a Claude subscription (OAuth login) -- both are verified working through the local proxy. Codex support is planned next.

Download both files from Releases into the same directory:

- `hailmary-fabric-alpha-macos-arm64.tar.gz`
- `SHA256SUMS`

Run these commands in that download directory:

```bash
shasum -a 256 -c SHA256SUMS
tar -xzf hailmary-fabric-alpha-macos-arm64.tar.gz
cd hailmary-fabric-alpha-macos-arm64
shasum -a 256 -c SHA256SUMS
sh install.sh
./fabric.dist/fabric claude --repo /path/to/your/repo
```

The first `shasum` checks the downloaded archive. The second `shasum` checks the extracted files.

The binary is unsigned and not notarized. Run `sh install.sh` before running `./fabric.dist/fabric`. The installer removes quarantine metadata from `./fabric.dist` only. It does not use sudo, edit PATH, modify your repo, or start Claude.

## Safety

- no hosted Fabric service
- no repo upload to HailMary
- local state under `.fabric/`
- proxy binds `127.0.0.1` only
- run `claude` directly to bypass Fabric
- selected context still goes to your configured Claude provider during Claude Code sessions

## Status

This is a pre-1.0 test release. Early controlled API tests showed token savings on some tasks, but results vary by repo and task.

Source is private during this alpha.
