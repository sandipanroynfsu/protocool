# Protocool 🚀

> **Watch the internet work, packet by packet.**  
> An interactive, high-fidelity network protocol visualizer and Wireshark-style packet decoder for learning how core internet protocols operate.

---

## 🌟 What is Protocool?

**Protocool** is a faithful, enhanced reconstruction of the interactive networking education application originally hosted at `protocol-explorer-alpha.vercel.app`. It allows engineers, students, and networking enthusiasts to inspect the internet at the microscopic level: from DNS queries and TCP three-way handshakes to TLS record negotiation, HTTP transactions, and packet-level byte encoding.

### 📚 Supported Protocol Lessons (14 Protocols)

1. **HTTP** (`Layer 7 - Application`): Client Request, DNS Resolution, TCP Connection, HTTP Exchange, Page Rendering
2. **HTTPS** (`Layer 7 - Security`): Secure Request, DNS Lookup, TCP Handshake, TLS Handshake, Encrypted Exchange, Padlock Rendering
3. **TCP** (`Layer 4 - Transport`): Three-way handshake, sequence numbers, window sizing, lost segment retransmission, SACK, teardown
4. **UDP** (`Layer 4 - Transport`): Connectionless streaming, datagram flow, packet loss resilience, VoIP/video tradeoffs
5. **IP** (`Layer 3 - Network`): Subnet checking, ARP resolution, header fields, TTL decrement, NAT translation
6. **DNS** (`Layer 7 - Application`): Root hints, TLD lookups, recursive queries, A/AAAA records, caching
7. **DHCP** (`Layer 7 - Application`): DORA sequence (Discover, Offer, Request, Acknowledge), lease renewal
8. **ICMP** (`Layer 3 - Network`): Echo Request / Echo Reply (ping), TTL exceeded (traceroute), error reporting
9. **SMTP** (`Layer 7 - Application`): Mail transfer, EHLO handshake, MAIL FROM, RCPT TO, DATA transmission
10. **POP3** (`Layer 7 - Application`): Mail retrieval, authentication, STAT, RETR, DELE commands
11. **IMAP** (`Layer 7 - Application`): Two-way mailbox sync, folder navigation, flags, message fetch
12. **FTP** (`Layer 7 - Application`): Control connection vs active/passive data connections, file streaming
13. **SSH** (`Layer 7 - Security`): Key exchange, host verification, Diffie-Hellman, encrypted interactive shell
14. **TLS/SSL** (`Layer 6/7 - Security`): Cipher suite negotiation, certificates, asymmetric key exchange, symmetric session keys

---

## 🛠️ Architecture & REA Evidence Summary

The application was analyzed and reverse-engineered using **REA (Reverse Engineer Anything)**:

- **Browser Scenario Capture Evidence**: `ev_8d57516e2b85364c3a779dfc60bf67e96e9be93d9d897dff1b4a5f38b1726d18`
- **JavaScript Application Graph Evidence**: `ev_6d3d22f497741f1745c1242979153a086838b49202b1d8fd5ac7b8dfd42b5301` & `ev_052a5ca71ca2eb05f0a4f5c040d6cfa1cba8e3b2e36b8e3a24b07fb3e7cfab22`
- **Framework**: High-performance Vanilla JavaScript ESM bundle without heavy virtual DOM overhead.
- **Topology & Animation**: Dynamic SVG vector path interpolation animating packet movement between client, router, DNS server, internet gateway, and destination servers.
- **Wireshark Wire Decoder**: Decodes frame layers byte-by-byte (Ethernet II, IPv4, TCP/UDP headers, TLS records, application payloads).
- **Internationalization (i18n)**: Fully supported across 15 languages (English, Spanish, Portuguese, French, German, Turkish, Ukrainian, Indonesian, Japanese, Simplified Chinese, Traditional Chinese, Korean, Hindi, Arabic, Hebrew) with RTL support.
- **Storage & State**: Clean local state using `protocool:progress:v1`, `protocool:theme`, `protocool:speed`, and `protocool:view`.

---

## 🚀 Quick Start

### 1. Run with Node.js Built-in Server
Protocool includes a zero-dependency, high-speed static server supporting gzip compression and MIME mappings:

```bash
# Start default server on port 3000
npm start

# Or specify a custom port
node server.js 8080
```

### 2. Open in your Browser
Navigate to:
```
http://localhost:3000
```

---

## 📂 Project Structure

```
Protocol Viewer/
├── assets/
│   ├── index.js               # Main Protocool engine (reactive state, packet generator, simulation)
│   ├── index.css              # Cyber-retro typography, variables, responsive layouts, themes
│   ├── iosevka-*.woff2        # Embedded low-latency monospace font family
│   ├── *-*.js                 # Dynamic language chunks (15 locales)
│   └── favicon.svg            # Custom Protocool vector branding icon
├── index.html                 # Main entrypoint with immediate dark/light theme loader
├── server.js                  # Zero-dependency, gzip-enabled Node.js server
├── package.json               # Project manifest and runner scripts
├── site.webmanifest           # Progressive Web App (PWA) manifest
└── README.md                  # Comprehensive documentation & REA reverse engineering ledger
```
"# protocool" 
