# Task 5: OSINT Investigation

## 1. Objective

The objective of this task is to understand Open Source Intelligence (OSINT) by collecting and analyzing publicly available information about a domain and documenting its digital footprint.

## 2. Target

- **Target:** google.com
- **Target type:** Public website domain
- **Scope:** Public domain registration information, DNS records, and HTTP response headers.

## 3. Tools Used

- **WHOIS:** To inspect publicly available domain registration information.
- **DIG:** To query DNS records.
- **CURL:** To inspect HTTP response headers.
- **Terminal:** To execute the commands and record observations.

## 4. Methodology

### Step 1: Domain Registration Lookup

Command:

```bash
whois google.com
```

Observation:

The output displayed domain registration details, registrar information, domain status codes, registration dates, and nameserver information.

### Step 2: DNS Information Gathering

Commands:

```bash
dig google.com A
dig google.com NS
dig google.com MX
```

Observations:

- The A record query returned IPv4 addresses.
- The NS record query identified the domain's nameservers.
- The MX record query returned a mail server entry.

DNS responses may vary depending on the resolver and time of the query.

### Step 3: HTTP Header Analysis

Command:

```bash
curl -I https://www.google.com
```

Observation:

The response included an HTTP status code and headers supplied by the website. These provide basic information about how the server responded to the request.

## 5. Findings

The investigation demonstrated that publicly accessible sources can reveal:

- Domain registration and registrar information.
- DNS addresses and nameserver records.
- Mail routing information published through DNS.
- HTTP response metadata.

These details can help build a basic picture of a domain's public-facing digital footprint.

## 6. Ethical Considerations

This exercise used public domain information and basic HTTP requests. It did not attempt to access private accounts, collect private personal information, bypass authentication, or exploit vulnerabilities.

Only information relevant to the stated investigation scope was collected.

## 7. Conclusion

This investigation improved my understanding of OSINT techniques and how publicly available domain, DNS, and HTTP information can be collected and analyzed.

It also demonstrated the importance of defining a target, recording findings accurately, and respecting privacy and authorization boundaries.

## 8. Evidence

Relevant terminal screenshots are included in the repository to support the recorded observations.
