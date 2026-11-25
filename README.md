# 🔍 OSINT Intelligence Tool

<div align="center">

### An Open-Source Intelligence Toolkit for Ethical Security Research

A Python-based OSINT toolkit for gathering, analyzing, and organizing publicly available information through modular intelligence workflows.

Built for cybersecurity learning, authorized investigations, and responsible security research.

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Linux-557C94?style=for-the-badge&logo=linux&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Purpose](https://img.shields.io/badge/Purpose-Educational-orange?style=for-the-badge)

</div>

---



---

## ⚠️ Ethical Disclaimer

> This tool is built **strictly for educational and ethical research purposes**.
> Only investigate phone numbers, emails, IPs, and usernames that **you own**
> or have **explicit written consent** to investigate.
> Unauthorized use may violate the **IT Act 2000 (India)** and similar
> cybercrime laws in other jurisdictions. The author accepts no liability for misuse.

---

## 📸 Demo

```
╭──────── OSINT Intelligence Tool — v1.0 ────────╮
│  1   Phone Number Lookup    ✔  ready            │
│  2   IP Address Lookup      ✔  ready            │
│  3   Email Intel            ✔  ready            │
│  4   Social Media Mapper    ✔  ready            │
│  5   Image OSINT + Steg     ✔  ready            │
│  6   Generate PDF Report    ✔  ready            │
│                                                  │
│  0   Exit                                        │
╰──────────────────────────────────────────────────╯
```

---

## ✨ Features

### 📱 Phone Intelligence
- Phone number validation and formatting
- Country, region, carrier, and line-type identification
- Timezone information and international number formatting
- External intelligence lookup integrations

### 🌐 IP Intelligence
- IP geolocation and network information
- ISP, ASN, reverse DNS, and timezone analysis
- VPN, proxy, and Tor detection where supported
- Geographic and network intelligence enrichment

### 📧 Email Intelligence
- Email format and domain validation
- Disposable email detection
- MX record and DNS analysis
- Email breach lookup integrations

### 👤 Username & Social Media Investigation
- Username searches across multiple platforms
- Platform availability checks
- Response status and timing analysis

### 🖼️ Image Intelligence
- EXIF and metadata extraction
- GPS location extraction when available
- Image analysis and steganography detection utilities
- Reverse image search references

### 📄 Intelligence Reporting
- Structured investigation reports
- Consolidated findings
- PDF report generation

## 🗂️ Project Structure

```
osint-tool/
├── main.py                    # Interactive menu (while True loop)
├── requirements.txt           # All Python dependencies
├── setup.py                   # Package installer
├── .env.example               # API key template (copy to .env)
├── .gitignore                 # Excludes secrets and output
│
├── utils/
│   ├── __init__.py
│   ├── config.py              # .env loader + API key validator
│   └── logger.py              # Coloured terminal output + banner
│
├── modules/
│   ├── __init__.py
│   ├── phone_lookup.py        # Phase 1 — Phone intelligence
│   ├── ip_intel.py            # Phase 2 — IP geolocation
│   ├── email_intel.py         # Phase 3 — Email analysis
│   ├── social_mapper.py       # Phase 4 — Username search
│   ├── avatar_fingerprint.py  # Phase 5 — Image OSINT + steg
│   └── report_generator.py    # Phase 6 — PDF report
│
├── data/
│   └── platforms.json         # 50+ social platform URL templates
│
├── tests/
│   ├── __init__.py
│   ├── test_phone.py          # Unit tests — phone module
│   └── test_ip.py             # Unit tests — IP module
│
├── output/                    # Scan results saved here (gitignored)
│   ├── scan_phone_*.json
│   ├── scan_ip_*.json
│   ├── scan_email_*.json
│   ├── scan_username_*.json
│   ├── scan_image_*.json
│   └── OSINT_Report_*.pdf
│
└── docs/
    └── USAGE.md               # Detailed usage guide
```

---

## 🚀 Installation

### Prerequisites
- Linux (Kali Linux recommended) or macOS
- Python 3.10+
- pip

### 1. Clone the repository
```bash
git clone https://github.com/nani-arise/osint-tool.git
cd osint-tool
```

### 2. Create and activate a virtual environment
```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Install system tools (Kali Linux)
```bash
sudo apt install steghide binwalk ruby -y
sudo gem install zsteg
```

### 5. Configure API keys
```bash
cp .env.example .env
nano .env
```

Configure the API keys required by the modules:

```env
NUMVERIFY_KEY=your_key_here
IPINFO_KEY=your_key_here
ABSTRACT_KEY=your_key_here
HIBP_KEY=your_key_here
```

### 6. Launch the application
```bash
python main.py
```

> **Note:** Some features require external API keys and additional system utilities. Availability may depend on your configuration and the services used.

## 🎯 Usage Examples

### 📱 Phone Number Intelligence
```text
Select option: 1
Enter phone number: +919876543210

Phone Intelligence Results
├── Country       : India (IN)
├── Carrier      : Airtel
├── Line Type    : Mobile
├── Timezone    : Asia/Kolkata
├── WhatsApp    : Likely
└── External References
    ├── Google Search
    └── Truecaller
```

### 🌐 IP Address Intelligence
```text
Select option: 2
Enter IP address: 8.8.8.8

IP Intelligence Results
├── City         : Mountain View
├── Region       : California
├── Country      : United States
├── Coordinates  : 37.386051, -122.083855
├── ISP          : Google LLC
├── ASN          : AS15169
└── Proxy/VPN   : No

External References:
├── Google Maps
└── Shodan
```

### 📄 PDF Report Generation
```text
Select option: 6
Enter report label: investigation_001

Report Generated Successfully
File: output/OSINT_Report_investigation_001.pdf
```

> **Note:** Outputs shown above are illustrative examples. Actual results may vary depending on API availability, input data, and configuration.

## 🔑 API Configuration

Some features use external APIs to enrich intelligence results. API keys are optional for certain modules, depending on the configured integrations.

| Service | Purpose | Configuration |
|---|---|---|
| NumVerify | Phone number intelligence | `NUMVERIFY_KEY` |
| IPInfo | IP geolocation and network intelligence | `IPINFO_KEY` |
| AbstractAPI | Email validation and deliverability | `ABSTRACT_KEY` |
| HaveIBeenPwned | Email breach lookup | `HIBP_KEY` |
| WhoisXML | Domain WHOIS intelligence | Optional API integration |

### Configuration

- API keys are stored in the local `.env` file.
- Never commit API keys, tokens, or credentials to GitHub.
- Some modules provide limited functionality without API credentials.
- API availability and usage limits depend on the respective service providers.

See `.env.example` for the required configuration variables.

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| **Programming Language** | Python 3.11 |
| **Terminal Interface** | Rich |
| **HTTP & Networking** | Requests, aiohttp |
| **Phone Intelligence** | phonenumbers |
| **DNS & Network Analysis** | dnspython |
| **Image Processing** | Pillow, ImageHash |
| **Steganography Analysis** | steghide, zsteg, binwalk |
| **PDF Reporting** | ReportLab |
| **Configuration Management** | python-dotenv |
| **Testing** | pytest |
| **Environment** | Linux, Kali Linux |



## 🧪 Testing

This project uses `pytest` for running automated tests.

### Run the test suite

```bash
pytest tests/ -v
```

### Run tests with detailed output

```bash
pytest tests/ -v -s
```

### Run a specific test file

```bash
pytest tests/test_phone.py -v
```

> Test coverage depends on the test cases implemented in the `tests/` directory.



## 📚 Key Learning Outcomes

Building this project helped me explore and implement concepts across cybersecurity, networking, and Python development.

- **OSINT Methodology** — Gathering and correlating publicly available intelligence.
- **Asynchronous Programming** — Using `asyncio` and `aiohttp` for concurrent operations.
- **API Integration** — Working with REST APIs, authentication, response handling, and error management.
- **Network Intelligence** — Understanding IP geolocation, DNS records, ISP information, and ASN data.
- **Digital Image Forensics** — Extracting EXIF metadata and identifying embedded information.
- **Steganography Analysis** — Exploring LSB techniques and tools such as `steghide`, `zsteg`, and `binwalk`.
- **Perceptual Hashing** — Understanding image similarity through perceptual fingerprints.
- **Python Project Structure** — Organizing modular code, dependencies, and virtual environments.
- **Security Practices** — Managing environment variables, API credentials, and responsible investigation workflows.
- **Report Generation** — Creating structured PDF reports using ReportLab.

## ⚖️ Legal & Ethical Use

This tool is developed for educational purposes, cybersecurity research, and authorized investigations involving publicly available information.

### Responsible Usage
- Use the tool only for lawful purposes.
- Investigate only information you are authorized to access.
- Respect privacy, applicable laws, and platform terms of service.
- Obtain appropriate permission before conducting investigations involving individuals or organizations.

### Scope & Limitations
- The tool relies on publicly accessible sources and configured third-party services.
- Results may be incomplete, inaccurate, outdated, or unavailable.
- Certain features depend on external APIs, network availability, and service limitations.
- The tool does not guarantee the accuracy of intelligence findings.

### Disclaimer
The developer assumes no responsibility for misuse, unauthorized investigations, privacy violations, or damages resulting from the use of this software. Users are solely responsible for ensuring their activities comply with applicable laws and regulations.

## 📜 License

MIT License — see [LICENSE](LICENSE) for details.

---

## 👨‍💻 Author

## 👨‍💻 Author

**Y S Nandish**  
Cybersecurity Engineering Student

Interested in cybersecurity, threat detection, security research, Linux, and building practical security tools.

- GitHub: [@nani-arise](https://github.com/nani-arise)

---

<div align="center">

*Built with ❤️ for learning, security research, and responsible use.*

</div>
