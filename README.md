# Network-Analysis-Using-Wireshark

## Scenario

This lab is published through DigitalCorpora.org. Thanks to digitalcorpora.org and to Ajoy Ghosh at the UNSW Canberra for this work!

You are a security administrator at the prestigious (and fictional) Nitroba State University.

Nitroba’s IT department received an email from Lily Tuckrige, a teacher in the Chemistry Department. Tuckrige has been receiving harassing emails and she suspects that they are being sent by a student in her class Chemistry 109, which she is teaching this summer. The email was received at Tuckridge’s personal email account, lilytuckrige@yahoo.com. She took a screenshot of the web browser and sent it in.

The system administrator who received the complaint wrote back to Tuckridge that Nitroba needed the full headers of the email message. Tuckridge responded by clicking the “Full message headers” button in Yahoo Mail and sent in another screen shot, this one with mail headers.

The mail header shows that the mail message originated from the IP address 140.247.62.34, which is a Nitroba student dorm room. Three women share the dorm room. Nitroba provides an Ethernet connection in every dorm room but not Wi-Fi access, so one of the women’s friends installed a Wi-Fi router in the room. There is no password on the Wi-Fi.

Because several email messages appear to come from the IP address, Nitroba decides to place a network sniffer on the ethernet port. All of the packets are logged. On Monday 7/21 Tuckridge received another harassing email. But this time instead of receiving it directly, the perpetrator sent it through a web-based service called “willselfdestruct.com.” The website briefly shows the message to Tuckridge, and then the website reports that the “Message Has Been Destroyed.”

You have been given the screen shots, the packets that were collected from the Ethernet tap, and the Chem 109 roster. Your job is to determine if one of the students in the class was responsible for the harassing email and to provide clear, conclusive evidence to support your conclusion. Please find slides with more details and the required pcap file through https://digitalcorpora.org/corpora/scenarios/nitroba-university-harassment-scenario/

## Objectives

- Verify forensic integrity of the evidence
- Analyze captured network traffic (.pcap)
- Identify malicious HTTP communications
- Reconstruct deleted web messages
- Trace the originating device using IP and MAC addresses
- Correlate network evidence with user activity
- Produce a complete forensic investigation report

## Skills Demonstrated

- Network Forensics
- Packet Analysis
- Wireshark
- HTTP Stream Reconstruction
- Evidence Integrity Verification (SHA-256)
- Digital Investigation Methodology
- Timeline Analysis
- IOC (Indicator of Compromise) Identification
- Documentation & Reporting

## Tools Used

- Wireshark 4.4.1
- Windows Command Prompt
- SHA-256 Hash Verification (certutil)

## Investigation Workflow

```
Evidence Acquisition
        │
        ▼
SHA-256 Hash Verification
        │
        ▼
Load PCAP into Wireshark
        │
        ▼
Locate Suspicious Traffic
        │
        ▼
Analyze HTTP Requests
        │
        ▼
Extract Network Artifacts
(IP • MAC • User-Agent)
        │
        ▼
Follow HTTP Stream
        │
        ▼
Reconstruct Deleted Message
        │
        ▼
Search Related Email Activity
        │
        ▼
Correlate Browser Cookies
        │
        ▼
Identify Responsible User
```

## Key Investigation Steps

### 1. Evidence Verification

Verified the SHA-256 hash of the PCAP file to ensure the evidence had not been altered before analysis.

### 2. Packet Analysis

Opened the capture in Wireshark and searched packet contents for unique message strings associated with the harassment.

### 3. HTTP Stream Reconstruction

Used **Follow HTTP Stream** to reconstruct the complete communication exchanged with the anonymous messaging website.

### 4. Network Artifact Collection

Extracted critical forensic artifacts including:

- Source IP Address
- MAC Address
- User-Agent
- HTTP POST Requests
- Cookie Values
- Email Identifiers

### 5. Correlation Analysis

Correlated browser cookies, email identifiers, and HTTP activity across multiple packets to attribute the activity to a single device.

### 6. Attribution

Combined all recovered evidence to identify the source responsible for the anonymous messages.

# Key Findings

- Successfully validated forensic evidence using SHA-256.
- Reconstructed deleted anonymous messages from HTTP traffic.
- Identified the originating device using IP and MAC addresses.
- Correlated browser cookies with network activity.
- Demonstrated how packet analysis can reveal user attribution despite attempts to remain anonymous.
