# Task 3: Networking & Reconnaissance

## Objective
To understand basic networking concepts and perform reconnaissance using commands to gather publicly available information about a domain.

## Target
`google.com`

## Tools Used
- `nslookup` — DNS lookup
- `dig` — DNS record queries
- `whois` — Domain registration lookup
- `curl` — HTTP response header inspection

## 1. DNS Lookup Using nslookup

**Command:**
```bash
nslookup google.com
```

**Observation:**

The command returned multiple IPv4 addresses and an IPv6 address for Google. The DNS server used for the query was `192.168.31.1`.

## 2. DNS Record Analysis Using dig

### A Record
```bash
dig google.com A
```
The query returned six IPv4 A records, and the response status was `NOERROR`.

### NS Record
```bash
dig google.com NS
```
The response listed four nameservers:
- ns1.google.com
- ns2.google.com
- ns3.google.com
- ns4.google.com

### MX Record
```bash
dig google.com MX
```
The response listed `smtp.google.com` with priority 10.

## 3. Domain Registration Lookup Using whois

**Command:**
```bash
whois google.com
```

**Observation:**

The output displayed domain registration information, the registrar (MarkMonitor Inc.), registration dates, domain status codes, and nameserver details.

## 4. HTTP Response Header Analysis

**Command:**
```bash
curl -I https://google.com
```

**Observation:**

The server returned `HTTP/2 301`, redirecting the request to `https://www.google.com/`.

The second command:
```bash
curl -I https://www.google.com
```

returned `HTTP/2 200`, indicating a successful response.

## Conclusion

Through this practical, I learned how DNS resolves domain names, how to inspect A, NS, and MX records, how to retrieve public domain registration information, and how to examine HTTP response headers using curl.

This exercise improved my understanding of networking fundamentals and basic reconnaissance techniques.

## Scope

This exercise used basic DNS queries, a public WHOIS lookup, and HTTP header requests. No vulnerability exploitation was performed.
