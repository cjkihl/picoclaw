# Updating PicoClaw from Source

This document describes how to update PicoClaw when built from source instead of the apt package.

## Current Setup

- **Source location:** `~/a/picoclaw`
- **Binary location:** `/usr/bin/picoclaw`
- **Go version:** 1.25.8 (installed at `/usr/local/go`)

## How to Update

```bash
# 1. Navigate to source directory
cd ~/a/picoclaw

# 2. Pull latest changes
git pull

# 3. Rebuild
make build

# 4. Install new binary
sudo cp build/picoclaw-linux-arm64 /usr/bin/picoclaw
sudo chmod +x /usr/bin/picoclaw
```

## Verify

```bash
picoclaw version
```

## Troubleshooting

If you see "command not found", use the full path:
```bash
/usr/bin/picoclaw version
```

Make sure `/usr/local/go/bin` is in your PATH if you need to run Go manually:
```bash
export PATH=$PATH:/usr/local/go/bin
```
