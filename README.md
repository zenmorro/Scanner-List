# Scanner List

Auto-generated public threat-intelligence feed of IP addresses caught by a
Node.js honeypot (SSH brute-force, scanner/recon paths, web-app probes).

**Last updated:** 2026-06-25T04:00:01.846Z
**Entries:** 437

## Files

| File | Description |
|------|-------------|
| [`blocklist.txt`](./blocklist.txt) | One IP per line. `#` lines are comments. Ready for firewall/ipset URL feeds. |
| [`blocklist.csv`](./blocklist.csv) | `ip,type,categories,blocked_at,hit_count`. Categories follow the [AbuseIPDB](https://www.abuseipdb.com/categories) scheme. |

## Usage

Plain IP list (strips comments):

```bash
curl -s https://raw.githubusercontent.com/zenmorro/Scanner-List/main/blocklist.txt | grep -v '^#'
```

Load into ipset:

```bash
ipset create honeypot-feed hash:ip -exist
curl -s https://raw.githubusercontent.com/zenmorro/Scanner-List/main/blocklist.txt | grep -v '^#' | while read ip; do ipset add honeypot-feed "$ip" -exist; done
```

## Disclaimer

These IPs hit a honeypot and never a production service, so hits are
high-confidence malicious. Still, addresses can be spoofed, shared (CGNAT),
or reassigned over time — use as one signal, not absolute truth.

---
*Generated automatically — do not edit by hand.*
