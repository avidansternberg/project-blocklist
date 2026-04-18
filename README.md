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

### Domain Lists

| File                        | Description                         |
|-----------------------------|-------------------------------------|
| `ads.csv`                   | General advertising domains         |
| `abuse.csv`                 | Known abusive domains               |
| `malware.csv`               | Malware distribution domains        |
| `scam.csv`                  | Scam and fraud domains              |
| `hate-and-junk.csv`         | Hate speech and problematic content |
| `neofascism.csv`            | Fascist/extremist domains           |
| `racism.csv`                | Racist domains                      |
| `suspicious.csv`            | Suspicious domains                  |
| `gambling.csv`              | Online gambling domains             |
| `tracker.csv`               | General tracker domains             |
| `spotify-ads.csv`           | Spotify ad domains                  |
| `spotify-ads-tracking.csv`  | Spotify tracking domains            |
| `mobile_tracker.csv`        | Mobile tracker domains              |
| `whatsapp.csv`              | WhatsApp-related tracking           |
| `tiktok.csv`                | TikTok tracking domains             |
| `google-amp-hosts.csv`      | Google AMP tracking                 |
| `xiaomi-ads.csv`            | Xiaomi ad/tracker domains           |
| `avg-avast-data-mining.csv` | AVG/Avast data collection           |
| `d3ward.csv`                | D3ward blocklist                    |
| `domain_whitelist.csv`      | Whitelist for domains               |

### IP Lists

| File                   | Description                     |
|------------------------|---------------------------------|
| `abusive-ips.v4.csv`   | Abusive IPv4 addresses          |
| `abusive-ips.v6.csv`   | Abusive IPv6 addresses          |
| `smtp-abuse.v4.csv`    | SMTP abuse IPv4 (spam, testing) |
| `smtp-abuse.v6.csv`    | SMTP abuse IPv6                 |
| `server-tester.v4.csv` | Server testers IPv4             |
| `server-tester.v6.csv` | Server testers IPv6             |
| `mullvad.v4.csv`       | Mullvad VPN IPv4                |
| `mullvad.v6.csv`       | Mullvad VPN IPv6                |
| `archives.csv`         | Archived IP data                |

### User Lists

| File                       | Description            |
|----------------------------|------------------------|
| `toxic-fediverse-user.csv` | Toxic Fediverse users  |
| `fedi-racist-user.csv`     | Racist Fediverse users |
| `toxic-discord.csv`        | Toxic Discord users    |
| `scam-mail.csv`            | Scam email addresses   |

## Usage

### Pi-hole

Add the raw URLs to your Pi-hole blocklist:

```text
https://raw.githubusercontent.com/USER/PROJECT/branch/domain_lists/scam.csv
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
