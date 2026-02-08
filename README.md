# memoryco releases

Pre-built binaries and install tooling for [memoryco](https://memoryco.ai) — cognitive memory for AI.

## Install

```bash
curl -fsSL https://memoryco.ai/install.sh | sh
```

The installer downloads the right binary for your platform, caches the embedding model, and walks you through initial setup.

## Supported platforms

| Platform | Architecture | Target |
|----------|-------------|--------|
| macOS | Apple Silicon | `aarch64-apple-darwin` |
| macOS | Intel | `x86_64-apple-darwin` |
| Linux | x86_64 | `x86_64-unknown-linux-gnu` |
| Linux | ARM64 | `aarch64-unknown-linux-gnu` |

## Manual download

Grab the latest binary from [Releases](../../releases/latest), extract it, and put it in your PATH:

```bash
tar xzf memoryco-v*.tar.gz
chmod +x memoryco
mv memoryco ~/.local/bin/
```

## Verify checksums

Each release includes a `checksums.sha256` file:

```bash
sha256sum -c memoryco-v1.0.0-checksums.sha256
```

## Configuration

Add memoryco to your MCP client (e.g., Claude Desktop):

```json
{
  "mcpServers": {
    "memoryco": {
      "command": "memoryco",
      "args": ["serve"]
    }
  }
}
```

Or run `memoryco install` to auto-detect and configure all supported clients.

## Environment variables

| Variable | Default | Description |
|----------|---------|-------------|
| `MEMORY_HOME` | `~/.memoryco` | Where brain.db and config live |
| `MEMORYCO_VERSION` | latest | Pin install script to a specific version |
| `MEMORYCO_DIR` | `~/.local/bin` | Override install directory |

## Links

- **Website**: [memoryco.ai](https://memoryco.ai)
- **Architecture**: [memoryco.ai/architecture](https://memoryco.ai/architecture.html)
- **Pricing**: [memoryco.ai/pricing](https://memoryco.ai/pricing.html)
