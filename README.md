# Porkbun DNS Management Skill for OpenClaw

Manage Porkbun DNS records and domains via API v3.

## Overview

This skill enables OpenClaw to manage DNS records on Porkbun's DNS service. It includes a CLI tool for reliable, deterministic DNS operations.

## Installation

### For OpenClaw Users

Installation is available via clawhub.ai: `openclaw skills install porkbun-dns`

### Manual Installation

1. Download or clone this repository
2. Create `~/.config/porkbun/config.json` with your credentials (see Setup below)
3. The CLI tool is available at `scripts/porkbun-dns.js`

## Setup

### 1. Get API Keys

1. Log in to Porkbun
2. Visit https://porkbun.com/account/api
3. Generate API credentials (both public and secret keys)

### 2. Configure Credentials

**Option A: Config file (recommended)**
```bash
mkdir -p ~/.config/porkbun
cat > ~/.config/porkbun/config.json << EOF
{
  "apiKey": "your-pk1-api-key-here",
  "secretApiKey": "your-sk1-secret-key-here"
}
EOF
```

**Option B: Environment variables**
```bash
export PORKBUN_API_KEY="your-pk1-api-key-here"
export PORKBUN_SECRET_API_KEY="your-sk1-secret-key-here"
```

**Important:**
- These keys are sensitive - never commit them to git or share publicly
- The config file is read automatically if present
- Environment variables take precedence over config file
- Store credentials in `~/.config/porkbun/` which is excluded from git

### 3. Enable API Access

For each domain you want to manage:
1. Go to Domain Management on Porkbun
2. Click Details next to the domain
3. Enable "API Access"

## Usage

The skill integrates with OpenClaw and provides automated DNS management. Common operations:

- **Create records:** A, AAAA, CNAME, MX, TXT, and more
- **List domains and records**
- **Update existing records**
- **Delete records**
- **Batch operations by type/subdomain**

Example conversations:
- "Create an A record for www.example.com pointing to 1.1.1.1"
- "Update the MX record for example.com to use Google Workspace"
- "Delete all TXT records for old.example.com"

## Features

- **Full API v3 support:** All Porkbun DNS endpoints
- **CLI tool included:** Deterministic operations via `scripts/porkbun-dns.js`
- **Comprehensive documentation:** Reference guides for all record types
- **Batch operations:** Edit/delete multiple records at once
- **Common patterns:** Pre-built workflows for websites, email, dynamic DNS

## Documentation

Inside the skill:
- **CHANGELOG.md** - Version history and changes
- **SKILL.md** - Main usage guide
- **references/dns-record-types.md** - Complete DNS record reference
- **package.json** - Skill metadata and environment requirements

Online:
- [Porkbun API Documentation](https://porkbun.com/api/json/v3/documentation)
- [OpenClaw Skills](https://clawhub.ai/)

## Development

### Repository Structure

```
porkbun/
├── SKILL.md                    # Main skill documentation
├── scripts/
│   └── porkbun-dns.js         # CLI tool
└── references/
    └── dns-record-types.md    # DNS reference
```

### Building the .skill file

```bash
cd ~/.openclaw/workspace/skills/public/porkbun
zip -r ../porkbun.skill SKILL.md scripts/ references/
```

### Testing

Test connection:
```bash
node scripts/porkbun-dns.js ping
```

List your domains:
```bash
node scripts/porkbun-dns.js list
```

## Contributing

This skill is maintained for the OpenClaw community. For issues or improvements:
1. Check this repository
2. Open an issue or pull request

## License

Provided as-is for use with OpenClaw.

## Links

- [OpenClaw](https://docs.openclaw.ai/)
- [ClawHub](https://clawhub.ai/)
- [Porkbun](https://porkbun.com/)
- [Theta42](https://theta42.com/)