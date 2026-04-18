# Blocklist Project

A collection of domain, IP, and user blocklists for Pi-hole, AdGuard, and other DNS-based ad/tracker blockers.

## Overview

This project provides curated blocklists for blocking various categories of unwanted content:

- **Scam & Fraud**: Known scam domains and email addresses
- **Hate & Junk**: Hate speech, harassment, and problematic communities
- **Malware**: Known malware distribution domains
- **Neofascism**: Fascist and extremist domains spreading hate
- **Racism**: Racist domains and content
- **Abuse**: Known abusive services and infrastructure
- **Suspicious**: Suspicious domains requiring caution
- **Tracking**: Various tracker domains (Spotify, mobile, WhatsApp, TikTok, etc.)
- **Ads**: Advertising domains
- **Gambling**: Online gambling domains
- **IP Lists**: Known abusive IPs, SMTP abusers, server testers

## Directory Structure

```text
.
├── domain_lists/     # Domain-based blocklists
├── ip_lists/         # IP-based blocklists (IPv4 & IPv6)
├── user_lists/       # User-based blocklists (Fediverse, Discord)
├── example_usage/    # Example configurations
│   └── rspamd/       # Rspamd email filter configs
└── split.sh         # Script to split large IP lists
```
.
├── domain_lists/     # Domain-based blocklists
├── ip_lists/         # IP-based blocklists (IPv4 & IPv6)
├── user_lists/       # User-based blocklists (Fediverse, Discord)
└── example_usage/    # Example configurations
    └── rspamd/       # Rspamd email filter configs
```

### AdGuard Home

Use the same URL format in AdGuard Home's blocklist settings.

### Rspamd

Example configurations are provided in `example_usage/rspamd/`. Copy the relevant config files to your Rspamd configuration directory.

### DNS-Based Blockers

All CSV files can be used with any DNS-based blocker that accepts domain/IP lists.

## File Format

- Domain lists: Plain domain names (one per line)
- IP lists: IPv4/IPv6 addresses or CIDR ranges (one per line)
- Some files include comments prefixed with `:` (e.g., `:127.0.0.7:[Sternberg] Blacklisted: Scam`)

## Contributing

To add new entries:

1. Identify the appropriate category file in `domain_lists/`, `ip_lists/`, or `user_lists/`
2. Add the domain/IP/user to the relevant file
3. Follow the existing format
