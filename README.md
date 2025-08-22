Perfect. I’ll clean up everything and give you a **final, copy-paste ready README.md** that is professional, self-contained, and already includes the placeholders and proper markdown formatting (architecture diagram, demo screenshot, etc.).
I’ll also integrate the terminal screenshot you asked for so you can directly drop it in your `docs/` folder.

Here’s the final version:

---

```markdown
# Secure Chat System with Mutual TLS (mTLS)

A secure, terminal-based chat application developed in **C++** using **mutual TLS (mTLS)** with OpenSSL.  
This project demonstrates a production-grade security mechanism where both client and server authenticate each other using digital certificates, ensuring **confidentiality, authenticity, and integrity** of all communications.

---

## Features
- Mutual TLS authentication: both server and client verify certificates.  
- TLS 1.3 encrypted communication ensuring secure message exchange.  
- Multi-client support with concurrent connections via multithreading.  
- Modular C++ codebase designed for scalability and portability.  
- Tested on Linux systems with planned extension for Windows compatibility.  

---

## System Architecture

### High-Level Workflow
```

\[ Client 1 ] --
\[ Client 2 ] ---- mTLS ----> \[ Secure Chat Server (C++) ]
\[ Client N ] --/

````

### Architecture Diagram
*(Place your architecture diagram image here once available, e.g. `docs/architecture.png`)*  

```markdown
![Architecture Diagram](docs/architecture.png)
````

---

## Technology Stack

* **Language**: C++17
* **Security**: OpenSSL (TLS 1.3, X.509 certificates)
* **Concurrency**: POSIX Threads (Linux)
* **Build Tool**: CMake

---

## Project Structure

```
secure-chat-mtls/
│── src/
│   ├── server.cpp        # Server implementation
│   ├── client.cpp        # Client implementation
│   ├── tls_utils.cpp     # TLS and certificate utilities
│── include/              # Header files
│── certs/                # Certificates (generated locally)
│── scripts/
│   └── generate-certs.sh # Helper script for certificate generation
│── docs/
│   ├── architecture.png  # System diagram (placeholder)
│   └── demo.png          # Terminal session screenshot
│── CMakeLists.txt
│── README.md
```

---

## Prerequisites

* C++17 or later
* OpenSSL (>= 1.1.1)
* CMake build system
* Linux/Unix-like environment (initial testing platform)

---

## Installation

1. **Clone the repository**

```bash
git clone https://github.com/your-username/secure-chat-mtls.git
cd secure-chat-mtls
```

2. **Generate certificates**
   Run the helper script to create CA, server, and client certificates:

```bash
./scripts/generate-certs.sh
```

This generates:

* `ca.crt` – Certificate Authority
* `server.crt`, `server.key` – Server certificate and private key
* `client.crt`, `client.key` – Client certificate and private key

3. **Build the project**

```bash
mkdir build && cd build
cmake ..
make
```

---

## Usage

### Start the Server

```bash
./server ../certs/server.crt ../certs/server.key ../certs/ca.crt
```

### Start the Client

```bash
./client ../certs/client.crt ../certs/client.key ../certs/ca.crt
```

---

## Example Session (Terminal Demo)

Below is a demonstration of a secure session between a client and the server:

```markdown
![Terminal Demo](docs/demo.png)
```

---

## Security Considerations

* Both server and client must present valid certificates signed by the same Certificate Authority (CA).
* TLS 1.3 is enforced to guarantee strong encryption.
* Private keys (`.key` files) should be stored securely and excluded from version control.
* Only CA-signed clients are permitted to connect, preventing unauthorized access.

---

## Future Work

* Windows compatibility (OpenSSL + Winsock).
* WebSocket bridge using Boost.Beast for UI integration.
* Frontend UI (React-based) for improved user experience.
* Containerized deployment (Docker).
* Advanced authentication and user role management.

---

## Status

The terminal-based mTLS secure chat system is **fully functional**.
**Frontend UI integration is under active development.**

---

## License

MIT License © 2025 \[Anshuman Mahapatra]

```

---


