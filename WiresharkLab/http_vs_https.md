# HTTP vs HTTPS in Wireshark

This lab demonstrates the difference between HTTP (unencrypted) and HTTPS (encrypted using TLS) by capturing and analysing network packets in Wireshark.

---

## 1. HTTP Capture (http://neverssl.com)

### Observations:
- Protocol: HTTP
- Request: GET /
- Response: HTTP/1.1 200 OK
- Headers: fully visible
- Payload: visible in plain text (text/html)
- No encryption is used

### Example Findings:
- Host header is visible
- User-Agent is visible
- Full HTML body can be viewed in Wireshark

This shows that HTTP traffic is completely readable by anyone capturing the packets.

---

## 2. HTTPS Capture (https://example.com)

### Observations:
- Protocol: TLS 1.3
- Handshake messages observed:
  - Client Hello
  - Server Hello
  - Change Cipher Spec
- After handshake, packets switch to:
  - Application Data (encrypted)
  - QUIC Protected Payload (also encrypted)

### Important Note:
In TLS 1.3, Wireshark does not display "Encrypted Application Data" explicitly.  
It appears as Application Data, but this *is* the encrypted payload.

### Visibility:
- Headers: only basic metadata is visible
- Payload/body: completely encrypted
- No HTML, no sensitive data visible

This shows why HTTPS protects confidentiality and integrity.

---

## 3. Comparison Table

| Feature                | HTTP                         | HTTPS (TLS)                               |
|------------------------|------------------------------|--------------------------------------------|
| Port                   | 80                           | 443                                        |
| Encryption             | ❌ No encryption              | ✅ Encrypted (TLS)                         |
| Headers                | Fully visible                | Partially visible (sensitive = encrypted)  |
| Payload / Body         | Visible (plain text)         | ❌ Not visible (Application Data)          |
| Security               | Vulnerable to MITM           | Secure against eavesdropping & MITM        |
| Wireshark visibility   | GET / text/html in cleartext | Hello messages + encrypted data only       |

---

## 4. Summary

HTTP transmits all information in plain text, making it easy to intercept and read with Wireshark.  
HTTPS uses TLS encryption, meaning only handshake metadata can be seen; the actual payload remains encrypted.

This demonstrates why HTTPS is required for secure communication on the internet.
