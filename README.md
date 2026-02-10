# Porkbun DNS Management Skill

A skill for managing Porkbun DNS records and domains via API v3.

## For Users Using as a Skill

This skill can be installed in OpenClaw to enable DNS management capabilities. The skill includes a CLI tool for reliable DNS operations.

### Installing

1. Get the skill file: `porkbun.skill`
2. Install in OpenClaw: Follow clawhub.ai instructions for skill installation

### What It Does

- Create, read, update, delete DNS records on Porkbun
- List and manage domains
- Supports all common DNS record types (A, AAAAA, CNAME, MX, TXT, etc.)
- Includes CLI tool for deterministic operations
- Complete API v3 integration

## For Developers - Publishing to clawhub.ai

### Prerequisites

- A git repository at git.theta42.com
- SSH access or credentials for pushing

### Setup Steps

1. **Create the git repository at git.theta42.com**
   - Log into git.theta42.com
   - Create a new repository: `porkbun-skill` or similar
   - Initialize it (or let us push to it)

2. **Push the code**
   ```bash
   cd ~/.openclaw/workspace/skills/public/porkbun
   git remote add origin git@git.theta42.com:your-username/porkbun-skill.git
   git branch -M main
   git push -u origin main
   ```

3. **Publish to clawhub.ai**
   - Go to https://clawhub.ai/
   - Link your git.theta42.com repository
   - Add metadata (version, tags, description)
   - Publish the skill

4. **Update the skill file**
   - After publishing, the `.skill` file can be hosted on clawhub.ai
   - Users can install it from there

## Skill Contents

```
porkbun/
├── SKILL.md                    # Main skill documentation (required)
├── scripts/
│   └── porkbun-dns.js         # CLI tool for DNS operations
└── references/
    └── dns-record-types.md    # DNS record reference guide
```

## License

This skill is provided as-is for use with OpenClaw.

## Support

For API documentation: https://porkbun.com/api/json/v3/documentation
For skill issues: Check the source repository on git.theta42.com