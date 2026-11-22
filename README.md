# ModeCrypt

![ModeCrypt Banner](assets/modecrypt-banner.jpg)

### Cryptanalysis, Cryptographic Analysis & Attack Simulation Toolkit

ModeCrypt is a Python-based cryptographic research and security testing toolkit designed to explore cryptographic algorithms, analyze ciphertext, investigate encryption modes, and simulate cryptographic attacks.

It combines cryptanalysis, cryptographic analysis, and attack simulation in one modular framework.

The project is intended for cybersecurity students, penetration testers, developers, and security researchers who want to understand how cryptographic systems work, identify potential weaknesses, and study practical attack techniques in controlled environments.

> **Project Status:** Under Active Development — V1

---

## Overview

Cryptography is essential for protecting sensitive information, but incorrect implementations and insecure configurations can introduce vulnerabilities.

ModeCrypt aims to make cryptographic analysis and attack research more accessible through a collection of analysis modules and attack techniques.

The framework currently focuses on two main components:

- **Cryptanalysis Engine:** Analyzes encodings, hashes, ciphertext characteristics, block sizes, encryption modes, and algorithm information.
- **Cryptographic Attack Engine:** Provides implementations and analysis tools for studying weaknesses in different cryptographic modes.

ModeCrypt is modular, allowing individual analysis and attack modules to be developed, tested, and improved independently.

## Features

### 1. Cryptanalysis Engine

| Module                | Description                                                        |
| --------------------- | ------------------------------------------------------------------ |
| Encoding Analysis     | Detects and analyzes common encoding formats.                      |
| Hash Analysis         | Identifies possible hash algorithms based on hash characteristics. |
| Ciphertext Statistics | Analyzes ciphertext characteristics and statistical patterns.      |
| Block Analysis        | Examines block sizes and block-related properties.                 |
| Mode Analysis         | Analyzes potential encryption-mode characteristics.                |
| Algorithm Analysis    | Provides information about registered cryptographic algorithms.    |

### 2. Cryptographic Attack Engine

ModeCrypt includes attack and analysis modules for several encryption modes.

| Mode | Module                   | Purpose                                                          |
| ---- | ------------------------ | ---------------------------------------------------------------- |
| CBC  | Padding Oracle Attack    | Studies plaintext recovery through padding-validity information. |
| GCM  | Nonce Reuse Analysis     | Investigates security consequences of nonce reuse.               |
| GCM  | Authentication Analysis  | Examines authentication-related security properties.             |
| CTR  | Keystream Reuse Analysis | Studies vulnerabilities caused by keystream reuse.               |
| ECB  | Pattern Analysis         | Identifies repeated-block patterns in ciphertext.                |
| CFB  | Bit-Flipping Analysis    | Studies ciphertext modification and its effects on plaintext.    |
| OFB  | Keystream Analysis       | Examines keystream reuse and related weaknesses.                 |

**Note:** These modules have different implementation and validation levels. Their presence does not mean every possible attack scenario is supported.

## Architecture

ModeCrypt follows a modular architecture with two main engines.

```text
                  ModeCrypt
                      |
          +-----------+-----------+
          |                       |
   Cryptanalysis Engine    Cryptographic Attack Engine
          |                       |
   +------+------+          +----+----+----+----+
   |      |      |          |    |    |    |    |
Encoding Hash Statistics   CBC  GCM  CTR  ECB  CFB/OFB
Analysis Analysis Analysis   |    |    |    |    |
   |      |      |         Padding Nonce Keystream Pattern
Block  Mode  Algorithm     Oracle Reuse Reuse Analysis
Analysis Analysis Analysis
```

### Project Structure

```text
ModeCrypt/
├── src/
│   └── modecrypt/
│       ├── analysis/
│       ├── attacks/
│       │   ├── cbc/
│       │   ├── cfb/
│       │   ├── ctr/
│       │   ├── ecb/
│       │   ├── gcm/
│       │   └── ofb/
│       ├── core/
│       ├── crypto/
│       ├── labs/
│       ├── reports/
│       ├── utils/
│       ├── cli.py
│       └── main.py
├── tests/
├── pyproject.toml
└── README.md
```

## Installation

### Requirements

- Python 3.12 (used in current development and testing)
- pip
- Git

### Clone the repository

```bash
git clone https://github.com/ChhanunHean/Padding-Oracle-Attack-Lab.git
cd ModeCrypt
```

### Create a virtual environment

```bash
python3 -m venv .venv
```

Activate it:

**macOS / Linux**

```bash
source .venv/bin/activate
```

**Windows**

```powershell
.venv\Scripts\activate
```

### Install ModeCrypt

```bash
python -m pip install --upgrade pip
pip install -e .
```

## Usage

### View available commands

```bash
modecrypt --help
```

### Available command groups

```text
analyze
encoding
statistics
hash
block
mode
algorithm
attack
lab
gcm
ctr
ecb
cfb
ofb
```

### CBC Padding Oracle Lab

Run the built-in CBC padding oracle demonstration:

```bash
modecrypt attack cbc-padding-oracle --lab
```

The lab demonstrates how a padding oracle can expose plaintext without requiring knowledge of the AES secret key.

The current development environment has successfully demonstrated:

- Detection of the built-in CBC padding oracle.
- Recovery of all four ciphertext blocks.
- Independent padding verification of recovered blocks.
- Byte-for-byte comparison against the lab's known plaintext.

**Important:** The built-in lab is a controlled demonstration. It does not establish that every external CBC implementation is vulnerable.

## Testing

ModeCrypt uses pytest for automated testing and Ruff for code quality checks.

Run the complete test suite:

```bash
python -m pytest -v
```

Run code quality checks:

```bash
ruff check src tests
```

### Current Development Verification

Latest local verification:

| Check                      | Result            |
| -------------------------- | ----------------- |
| Automated tests            | 195 passed        |
| Ruff                       | All checks passed |
| CBC padding oracle lab     | SUCCESS           |
| CBC recovered blocks       | 4/4               |
| Known plaintext comparison | Match             |

These results represent the current development test environment, not a guarantee of complete security or correctness.

## Security and Responsible Use

ModeCrypt is intended for:

- Cryptographic education and research.
- Authorized security testing.
- Controlled attack simulations.
- Cryptographic implementation analysis.
- Understanding cryptographic weaknesses.

Only use ModeCrypt against systems, applications, and data that you own or have explicit permission to test.

The CBC padding oracle demonstration uses a built-in local lab. Do not use cryptographic attack techniques against unauthorized systems.

## Limitations

ModeCrypt is actively under development.

Current limitations include:

- Not every cryptographic attack scenario is implemented.
- Analysis results may identify candidates rather than definitive algorithms.
- Attack success depends on the target's cryptographic implementation and observable behavior.
- CBC padding oracle attacks require an oracle that reveals padding validity.
- Cryptographic attack modules require further independent validation.
- Passing automated tests does not prove the absence of implementation vulnerabilities.

## Roadmap

Planned development directions:

- [ ] Modular cryptanalysis architecture.
- [ ] Cryptographic attack module structure.
- [ ] CBC padding oracle lab.
- [ ] Initial analysis modules for multiple encryption modes.
- [ ] Independent CBC attack validation.
- [ ] Improve cryptographic analysis accuracy.
- [ ] Expand attack simulation capabilities.
- [ ] Improve reporting and evidence presentation.
- [ ] Expand automated test coverage.
- [ ] Documentation and usage examples.

Roadmap items may change as development progresses.

## Contributing

Contributions, bug reports, feature suggestions, and research discussions are welcome.

If you want to contribute:

1. Fork the repository.
2. Create a feature branch.
3. Implement your changes.
4. Add appropriate tests.
5. Run the test suite and Ruff.
6. Submit a pull request describing your changes.

## License

License: To be determined.

A license will be added before public distribution. Until then, do not assume that the repository grants permission to reuse, modify, or redistribute its code.

---

**ModeCrypt — Understand the weaknesses behind cryptographic security.**
