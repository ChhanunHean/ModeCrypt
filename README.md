# ModeCrypt

<p align="center">
  <img src="assets/modecrypt-banner.jpg" alt="ModeCrypt - Cryptanalysis and Attack Simulation Toolkit" width="100%">
</p>

<p align="center">
  <strong>Cryptanalysis, Cryptographic Analysis & Attack Simulation Toolkit</strong>
</p>

<p align="center">
  A cybersecurity research project exploring cryptographic algorithms, encryption modes, potential weaknesses, and attack techniques.
</p>

---

## About the Project

**ModeCrypt** is a Python-based cryptography research toolkit designed to combine cryptanalysis, cryptographic analysis, and attack simulation in one platform.

The project aims to help cybersecurity students, penetration testers, developers, and security researchers understand how cryptographic systems work, analyze their behavior, and explore potential vulnerabilities in different encryption algorithms and modes of operation.

ModeCrypt is currently in its early development stage. Its features, architecture, and testing capabilities will continue to evolve throughout development.

## Project Objectives

- Analyze cryptographic algorithms and encryption modes.
- Identify potential patterns and weaknesses in ciphertext.
- Explore cryptographic vulnerabilities through controlled attack simulations.
- Demonstrate how implementation mistakes can affect cryptographic security.
- Provide practical learning and research capabilities for cybersecurity enthusiasts.
- Build a modular platform that can be extended with additional cryptographic analysis techniques.

## Core Engines

ModeCrypt is designed around two main engines.

### 1. Cryptanalysis Engine

The Cryptanalysis Engine focuses on examining cryptographic data and identifying useful information about its structure and characteristics.

| Module | Description |
|---|---|
| Encoding Analysis | Analyze and identify common data encodings. |
| Hash Analysis | Examine hash formats and identify possible hash algorithms. |
| Ciphertext Statistics | Analyze byte frequencies, entropy, and data patterns. |
| Block Analysis | Examine ciphertext length and block-size characteristics. |
| Mode Analysis | Analyze patterns that may indicate encryption-mode behavior. |
| Algorithm Registry | Provide information about supported cryptographic algorithms. |

### 2. Cryptographic Attack Engine

The Cryptographic Attack Engine explores known weaknesses in encryption modes through controlled attack simulations.

| Encryption Mode | Planned Analysis / Attack |
|---|---|
| CBC | Padding Oracle Attack |
| GCM | Nonce Reuse and Authentication Analysis |
| CTR | Keystream Reuse Analysis |
| ECB | Repeated-Block and Pattern Analysis |
| CFB | Bit-Flipping and Malleability Analysis |
| OFB | Keystream Reuse Analysis |

**Important:** These attacks do not work against every implementation of an encryption mode. Their success depends on specific vulnerabilities, implementation behavior, and security configurations.

## Project Architecture

ModeCrypt is being developed with a modular architecture to make it easier to maintain, extend, and integrate new analysis and attack techniques.

```text
ModeCrypt/
│
├── assets/
│   └── modecrypt-banner.jpg
│
├── src/
│   └── modecrypt/
│       │
│       ├── analysis/
│       │   ├── _common.py
│       │   ├── algorithm_detection.py
│       │   ├── block_analysis.py
│       │   ├── encoding.py
│       │   ├── hash_analysis.py
│       │   ├── mode_detection.py
│       │   └── statistics.py
│       │
│       ├── attacks/
│       │   ├── base.py
│       │   ├── cbc/
│       │   ├── gcm/
│       │   ├── ctr/
│       │   ├── ecb/
│       │   ├── cfb/
│       │   └── ofb/
│       │
│       ├── core/
│       ├── crypto/
│       ├── labs/
│       ├── reports/
│       ├── utils/
│       │
│       ├── cli.py
│       └── main.py
│
├── tests/
│
├── pyproject.toml
└── README.md
```

*The architecture may change as development progresses.*

## Getting Started

### Requirements

- Python 3.12 or later
- Git
- pip

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/YOUR_USERNAME/ModeCrypt.git
cd ModeCrypt
```

**2. Create a virtual environment**

macOS / Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

**3. Install the project**

```bash
pip install -e .
```

## Usage

ModeCrypt is designed to provide a command-line interface for interacting with its cryptographic analysis and attack modules.

Display available commands:

```bash
modecrypt --help
```

The planned command groups include:

| Command Group | Purpose |
|---|---|
| `analyze` | General cryptographic analysis |
| `encoding` | Encoding analysis |
| `statistics` | Ciphertext statistics |
| `hash` | Hash analysis |
| `block` | Block-size analysis |
| `mode` | Encryption-mode analysis |
| `algorithm` | Algorithm information |
| `attack` | Cryptographic attack simulations |
| `lab` | Controlled practical experiments |

*Specific commands and options may change during development.*

## Research and Testing

Testing is an important part of ModeCrypt's development.

The project aims to use unit tests, independent test implementations, and controlled experiments to evaluate the correctness and reliability of its cryptographic analysis and attack modules.

Planned testing activities include:

- Testing different plaintext and ciphertext lengths.
- Evaluating encryption-mode behavior.
- Testing attack implementations against independent cryptographic implementations.
- Examining edge cases and invalid inputs.
- Evaluating how attack modules respond to unreliable or unavailable oracles.
- Verifying recovered results independently.

Run the test suite:

```bash
python -m pytest -v
```

Check code quality:

```bash
ruff check src tests
```

## Development Roadmap

ModeCrypt is under active development. The following roadmap represents the project's development direction.

- [ ] Improve the Cryptanalysis Engine.
- [ ] Expand encryption-mode analysis capabilities.
- [ ] Develop and improve cryptographic attack modules.
- [ ] Strengthen independent testing and verification.
- [ ] Improve command-line usability.
- [ ] Develop detailed analysis and reporting capabilities.
- [ ] Improve documentation and practical examples.
- [ ] Explore additional cryptographic research techniques.

## Security and Responsible Use

ModeCrypt is intended for educational purposes, cybersecurity research, and authorized security testing.

Users should only perform attack simulations against systems, applications, and cryptographic implementations they own or have explicit permission to test.

The project focuses on understanding cryptographic weaknesses and the conditions that make certain attacks possible.

## Limitations

- Cryptographic analysis does not always identify an algorithm or encryption mode with certainty.
- Hash identification produces possible candidates rather than guaranteed results.
- Attack success depends on the target implementation and its security properties.
- Some attack techniques require specific vulnerabilities, such as observable padding-validation behavior.
- Experimental results should not be treated as proof that a cryptographic implementation is secure or insecure.

## Contributing

Contributions, suggestions, and discussions are welcome.

If you are interested in improving ModeCrypt:

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Add or update relevant tests.
5. Submit a pull request.

## License

**License: To be determined.**

Until a license is added, all rights are reserved by the project owner. Please do not assume that the source code is available for unrestricted reuse or redistribution.

---

<p align="center">
  <strong>ModeCrypt</strong>
  <br>
  Understand the weaknesses behind cryptographic security.
</p>
