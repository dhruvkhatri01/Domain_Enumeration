# 🔍 DNS Enumeration Tool Using Python 

A command-line DNS Enumeration utility built with Python, designed to query common DNS records (A, AAAA, MX, TXT, SOA, CNAME) with retry logic, colorful terminal output, and optional JSON export. It is ideal for reconnaissance during penetration testing and network diagnostics.

---

## 🛠 Tools & Libraries Used

| Tool / Library | Purpose |
|----------------|---------|
| `argparse`     | CLI argument parsing |
| `dns.resolver` (dnspython) | DNS resolution and querying |
| `json`         | Saving results in structured format |
| `time`         | Measuring response time |
| `tqdm`         | Terminal progress bar |
| `colorama`     | Colored terminal output for better UX |

---

## 🚧 Challenges Faced

- **Timeouts and retries:** DNS resolution can be slow or fail depending on server response; implemented retry mechanism.
- **Record absence:** Some record types may not be present; handled `NoAnswer` and `NXDOMAIN` exceptions.
- **Cross-platform terminal compatibility:** Used `colorama` to handle colored outputs consistently across OSes.

---

## ✅ Advantages

- Supports multiple record types out of the box.
- Colored output makes result parsing easy during real-time usage.
- JSON export for storing or integrating results into further analysis tools.
- Retry mechanism improves robustness against temporary DNS server issues.

---

## ❌ Disadvantages

- No support for subdomain enumeration (could be added in future).
- Currently targets only a single domain at a time.
- Lacks GUI or web integration for non-technical users.

---

## 🔍 Use Case

- Reconnaissance in **penetration testing**.
- Validating DNS setup for **DevOps and Network Engineers**.
- Educational tool to understand how various DNS records work.
- Can be integrated with larger **automation pipelines** for passive recon.

---

## 📈 Relevance & Future Potential

DNS remains a core internet protocol. As cyber threats increase, **automated DNS enumeration tools** are becoming more essential in:
- Blue-team threat analysis
- Bug bounty reconnaissance
- Asset discovery in large infrastructures

The codebase can evolve to include:
- Subdomain brute-forcing
- DNSSEC checks
- Wildcard detection
- Zone transfer testing
- Multi-domain batch mode

---

## 💻 How to Run

### ✅ Prerequisites

Install required Python libraries:

```bash
pip install tqdm dnspython colorama argparse
```

---

Follow these steps:
```bash
python -m venv venv # To Create Environment Variable.
venv\Scripts\Activate # Activate It.
Python <file_name>.py --domain example.com # Run the Code
```

---

## 📁 Output Sample

```bash
[+] Starting DNS Enumeration for: example.com

Scanning DNS Records: 100%|█████████████████████████████████████| 6/6 [00:05<00:00,  1.10type/s]

A Records (0.123s):
  • 93.184.216.34
  TTL: 3600s

MX Records (0.111s):
  • 10 mx.example.com.

TXT Records (0.099s):
  • "v=spf1 include:_spf.example.com ~all"

[✓] Results saved to dns_results_example_com.json
```
## 🧪 JSON Format Sample

```bash
{
  "A": {
    "records": ["93.184.216.34"],
    "ttl": 3600,
    "response_time": 0.123
  },
  "MX": {
    "records": ["10 mx.example.com."],
    "ttl": 1800,
    "response_time": 0.111
  }
}
```

---

## ✅ Conclusion

This DNS Enumeration Tool is a lightweight, effective, and extendable utility for anyone working in networking, cybersecurity, or system administration. With support for multiple record types and detailed output, it offers a solid foundation for further DNS-based reconnaissance tools.
