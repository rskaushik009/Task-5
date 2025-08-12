# Task 5: Capture and Analyze Network Traffic Using Wireshark

## **Objective**
Capture live network packets using Wireshark and identify basic protocols and traffic types.

---

## **Tools Used**
- **Wireshark** (Free, Open-Source Packet Analyzer)

---

## **Steps Performed**

1. **Installed Wireshark**  
   - On Linux:  
     ```bash
     sudo apt update
     sudo apt install wireshark -y
     ```
     Allowed non-root packet capturing during installation.  
   - On Windows/macOS: Downloaded from [Wireshark.org](https://www.wireshark.org/).

2. **Started Wireshark**  
   - Selected the active network interface (**Wi-Fi / wlan0 / ETH0**).
   - Began live packet capture.

3. **Generated Network Traffic**  
   - Opened multiple websites in browser.
   - Ran `ping google.com` to generate ICMP packets.
   - Used `nslookup tryhackme.com` to generate DNS traffic.

4. **Stopped Capture**  
   - After ~1 minute, stopped the capture using the red square button.

5. **Filtered by Protocols**  
   - Used display filters: `dns`, `http`, `icmp`.
   - Observed corresponding packets.

6. **Saved Capture**  
   - Exported file as `Task_5.pcap`.

---

## **Protocols Identified**

| Protocol | Purpose | Example from Capture |
|----------|---------|----------------------|
| **DNS**  | Resolves domain names to IP addresses | Query: `www.tryhackme.com` to `8.8.8.8` |
| **HTTP** | Web traffic without encryption | `GET /index.html` request to a web server |
| **ICMP** | Network diagnostics (ping) | Echo Request to `142.250.183.206` (Google) |

---

## **Packet Details**
- **DNS Query:**  
  - Source: `192.168.29.1`  
  - Destination: `192.168.29.38`  
  - Query: `www.tryhackme.com`
  
- **HTTP Request:**  
  - Method: `GET`  
  - Destination Port: 80  
  - Host: Example web server

- **ICMP Packet:**  
  - Type: Echo Request (Type 8)  
  - Destination: Google server (`142.250.183.206`)

---

## **Conclusion**
The capture confirmed multiple protocol communications during typical internet activity.  
The `.pcap` file contains evidence of:
- Domain name resolution (DNS)
- Web browsing (HTTP)
- Network diagnostics (ICMP)

---

## **Deliverables**
- **Packet Capture File:** [`Task_5.pcap`](Task_5.pcap)  
- **Report:** Included above.
