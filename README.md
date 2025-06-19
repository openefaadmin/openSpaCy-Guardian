# openSpaCy-Guardian
NLP-based email intelligence engine for advanced spam, phishing, and sentiment analysis — built to integrate with OpenEFA.
**openSpacy-Guardian** is an intelligent, NLP-powered email analysis engine built to enhance spam filtering accuracy using SpaCy and modular Python-based detection layers. Designed to run alongside OpenEFA (or any modern email filtering gateway), openSpacy-Guardian brings contextual understanding, language analysis, and advanced threat recognition to your mail flow.
---
## 🔧 What Is It?
Traditional email filters often rely solely on rule-based systems and static signatures. **openSpacy-Guardian** introduces Natural Language Processing (NLP) into the mix — offering dynamic, context-aware email analysis that evolves with threats and language patterns.
Rather than replacing your mail filter, openSpacy-Guardian works **in tandem with systems like OpenEFA**, enriching your message stream with metadata, scoring, and classification that can be used in quarantine decisions, header tagging, and security audits.
---
## 🔍 Features
Each feature is modular and can be toggled on or off during configuration:
- 🧑‍🧠 **Phishing Detection**  
  Detects common phishing language and intent across subject lines and message bodies.
- 😐 **Sentiment Analysis**  
  Flags emails based on emotional tone — useful for identifying manipulative or hostile messages.
- 📣 **Marketing Classification**  
  Differentiates bulk marketing content from personal or transactional messages.
- 🧵 **Thread Awareness**  
  Identifies conversation context, reply patterns, and out-of-thread anomalies.
- 🌐 **Language Detection**  
  Detects and logs message language for multilingual classification and filtering.
- 🛥️ **Obfuscation Detection**  
  Flags suspicious text manipulation and encoded payloads often used in malicious campaigns.
- 📧 **BEC Module**  
  Targets business email compromise attempts using named entity recognition and tone analysis.
- 🚲 **PythonDNS Enhancement**  
  Extends DNS checks for spoof detection and domain intelligence.
---
## 🚀 Goals
- Provide intelligent, modular analysis of inbound email traffic.
- Enhance compatibility with OpenEFA scoring and quarantine logic.
- Offer a scriptable, headless install process for quick server deployment.
- Facilitate future integration with cloud logging, APIs, and dashboards.
---
## 📦 Project Structure
```bash
openSpacy-Guardian/
├── install.sh              # One-click installer script
├── requirements.txt        # Python dependencies
├── email_filter.py         # Core NLP processing logic
├── appy.py                 # Entry-point for message parsing
├── modules/                # Individual detection modules
│   ├── phishing.py
│   ├── sentiment.py
│   └── ...
├── config/                 # Optional runtime config and thresholds
└── docs/                   # Setup guides and architecture notes
```
---
## 🔄 Integration with OpenEFA
Once installed, openSpacy-Guardian is inserted **before your main filter**, typically receiving email via Postfix or Procmail. It scans and annotates the message with headers such as:
```
X-Spacy-Phishing-Score: 0.93
X-Spacy-Sentiment: negative
X-Spacy-Detected-Language: en
X-Spacy-BEC: suspicious
```
These headers are then interpreted by OpenEFA’s MailScanner or SpamAssassin components, contributing to spam scores or policy actions like quarantine or tagging.
---
## 📚 Documentation (coming soon)
- `docs/setup.md` – Manual setup & install options
- `docs/module-dev.md` – How to build and plug in new NLP modules
- `docs/openefa-integration.md` – Step-by-step guide for OpenEFA users
---
## 💡 Use Cases
- Email security appliances looking to expand beyond rule-based filters
- SOC teams needing deeper message analysis before manual review
- Self-hosted environments seeking anti-phishing enhancements
- Developers building modern mail security tools
---
## 🧠 Powered By
- [SpaCy](https://spacy.io/)
- Python 3
- Postfix or Procmail
- MariaDB/MySQL (optional for message metadata)
- Redis (optional for caching)
---
## 🛠️ Installation
Clone the repo and run the installer:
```bash
git clone https://github.com/openefaadmin/openSpacy-Guardian.git
cd openSpacy-Guardian
chmod +x install.sh
sudo ./install.sh
```
*Note: Installer currently targets CentOS 9 Stream with support for Ubuntu 22.04 coming soon.*
---
## 📄 License
This project is licensed under the [GNU GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.html).  
All modifications and forks must also remain open-source under the same license.
---
## 🤝 Contributing
Whether you're interested in creating new modules, improving NLP models, or integrating with other filters — we welcome your help. Feel free to submit issues or open a pull request.
---
## 🧰 Related Projects
- [OpenEFA](https://github.com/openefaadmin/eFa5) – The open-source email filtering appliance that inspired this engine
---
*Maintained by the SegueLogic team. Built to evolve with the next generation of email threats.*
