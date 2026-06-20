# DNS (Domain Name System) Commands

## Objective

Learn how domain names are translated into IP addresses and how Linux systems perform DNS resolution using standard networking utilities.

---

## What is DNS?

DNS (Domain Name System) is a distributed naming system that translates human-readable domain names into IP addresses.

Example:

```text
google.com → 192.178.193.113
```

Without DNS, users would need to remember numerical IP addresses instead of domain names.

---

## 1. host Command

The `host` utility is used to perform DNS lookups and display domain-related records.

### Syntax

```bash
host <domain_name>
```

### Example

```bash
host google.com
```

### Purpose

- Resolve domain names into IP addresses.
- Verify DNS functionality.
- View IPv4 and IPv6 records.

### Observation

The command returned multiple IPv4 addresses and IPv6 addresses associated with the Google domain.

---

## 2. dig Command

`dig` (Domain Information Groper) is an advanced DNS diagnostic tool commonly used by network engineers and system administrators.

### Syntax

```bash
dig <domain_name>
```

### Example

```bash
dig google.com
```

### Purpose

- Perform detailed DNS queries.
- Analyze DNS responses.
- Troubleshoot DNS resolution issues.
- Identify the DNS server handling the request.

### Important Sections

#### QUESTION SECTION

Shows the DNS record being requested.

```text
google.com. IN A
```

#### ANSWER SECTION

Contains the resolved IP addresses returned by the DNS server.

```text
google.com. IN A 192.178.xxx.xxx
```

#### SERVER

Displays the DNS server used to resolve the query.

```text
SERVER: 192.168.137.1#53
```

### Observation

The Raspberry Pi successfully resolved the Google domain through the configured DNS server.

---

## 3. Viewing DNS Configuration

Linux stores DNS server information in:

```bash
/etc/resolv.conf
```

### Command

```bash
cat /etc/resolv.conf
```

### Example Output

```text
nameserver 192.168.137.1
```

### Purpose

- Identify the DNS server currently used by the system.
- Verify network configuration.
- Troubleshoot DNS-related issues.

### Observation

The Raspberry Pi was configured to use:

```text
192.168.137.1
```

as its DNS resolver.

---

## Learning Outcome

Through this exercise, I learned:

- Fundamentals of the Domain Name System (DNS).
- How domain names are translated into IP addresses.
- DNS lookup using the `host` utility.
- Detailed DNS analysis using the `dig` utility.
- How Linux stores DNS configuration in `/etc/resolv.conf`.
- Basic DNS troubleshooting techniques on Raspberry Pi Linux.
- Relationship between DNS services and the TCP/IP networking stack.

---

## Commands Summary

| Command | Purpose |
|----------|----------|
| `host google.com` | Resolve a domain name to IP addresses |
| `dig google.com` | Detailed DNS query and analysis |
| `cat /etc/resolv.conf` | View configured DNS server |

---
