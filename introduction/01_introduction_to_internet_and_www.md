# Web Application Development — Lecture 01: Introduction to the Internet and the WWW
**University of Science and Technology of Hanoi (USTH)**  
**Information and Communication Technology Laboratory (ICTLab)**  
**Lecturers:** KIEU Quoc Viet, HUYNH Vinh Nam  
**Audience:** Web Application Development Students (Midterm Exam Preparation)

---

## Master Table of Contents
1. [Course Orientation & Midterm Study Strategy](#course-orientation--midterm-study-strategy)
2. [Section 1: Preview](#section-1-preview)
   - [Slide 1: Title Slide & Context](#slide-1-title-slide--context)
   - [Slide 2: Table of Contents](#slide-2-table-of-contents)
   - [Slide 3 & 4: What Happens When You Open a Website? (The 4 Steps)](#slide-3--4-what-happens-when-you-open-a-website-the-4-steps)
   - [Slide 5: The Internet Is Not the Web (Road vs. Traffic)](#slide-5-the-internet-is-not-the-web-road-vs-traffic)
3. [Section 2: How We Got Here (History & Evolution)](#section-2-how-we-got-here-history--evolution)
   - [Slide 6 & 7: 1969–1989: The Network Before the Web](#slide-6--7-19691989-the-network-before-the-web)
   - [Slide 8 & 9: 1969: Four Computers and One Strange Goal (ARPANET)](#slide-8--9-1969-four-computers-and-one-strange-goal-arpanet)
   - [Slide 10–12: 1974: TCP/IP (Addressing vs. Reliable Delivery)](#slide-1012-1974-tcpip-addressing-vs-reliable-delivery)
   - [Slide 13–15: 1983: DNS (Domain Name System)](#slide-1315-1983-dns-domain-name-system)
   - [Slide 16: 1990: One Person, Three Inventions (Tim Berners-Lee & The Birth of WWW)](#slide-16-1990-one-person-three-inventions-tim-berners-lee--the-birth-of-www)
   - [Slide 17: 1995–Today: From Pages to Applications](#slide-17-1995today-from-pages-to-applications)
4. [Section 3: The Internet Underneath (Core Infrastructure)](#section-3-the-internet-underneath-core-infrastructure)
   - [Slide 18 & 19: What a Protocol Is (Rules of a Conversation)](#slide-18--19-what-a-protocol-is-rules-of-a-conversation)
   - [Slide 20: What an IP Address Is](#slide-20-what-an-ip-address-is)
   - [Slide 21: IPv4 vs. IPv6](#slide-21-ipv4-vs-ipv6)
   - [Slide 22: Virtual vs. Real IP Address (NAT, Private vs. Public)](#slide-22-virtual-vs-real-ip-address-nat-private-vs-public)
   - [Slide 23: Domain Names and DNS in Practice](#slide-23-domain-names-and-dns-in-practice)
   - [Slide 24: The DNS Tree (Hierarchical Resolution)](#slide-24-the-dns-tree-hierarchical-resolution)
   - [Slide 25: Client and Server Architecture](#slide-25-client-and-server-architecture)
   - [Slide 26: Firewall and Proxy](#slide-26-firewall-and-proxy)
5. [Section 4: From Internet to Web (Web Technologies & Protocols)](#section-4-from-internet-to-web-web-technologies--protocols)
   - [Slide 27 & 28: Page, Site, Application](#slide-27--28-page-site-application)
   - [Slide 29: HTTP and HTML (Transport vs. Content)](#slide-29-http-and-html-transport-vs-content)
   - [Slide 30: One HTTP Conversation (Detailed Syntax of Request & Response)](#slide-30-one-http-conversation-detailed-syntax-of-request--response)
   - [Slide 31: Two Words in Every Conversation: Methods & Status Codes](#slide-31-two-words-in-every-conversation-methods--status-codes)
   - [Slide 32: Web Client: The Browser](#slide-32-web-client-the-browser)
   - [Slide 33: Web Server](#slide-33-web-server)
   - [Slide 34: Anatomy of a URL](#slide-34-anatomy-of-a-url)
   - [Slide 35: Home Page, Hyperlink, Tab](#slide-35-home-page-hyperlink-tab)
   - [Slide 36: Web Multimedia](#slide-36-web-multimedia)
   - [Slide 37: Search Engines & Web Crawlers](#slide-37-search-engines--web-crawlers)
   - [Slide 38: What a Browser Actually Does (The 4 Engine Phases)](#slide-38-what-a-browser-actually-does-the-4-engine-phases)
   - [Slide 39: Conclusion](#slide-39-conclusion)
6. [Midterm Exam Master Review: Key Differences, Traps & Exam Questions](#midterm-exam-master-review-key-differences-traps--exam-questions)

---

## Course Orientation & Midterm Study Strategy

This document provides a line-by-line, concept-by-concept breakdown of **Lecture 01: Introduction to the Internet and the WWW**. Every slide is unpacked with:
1. **Verbatim Slide Text & Diagram Deconstruction**: Exactly what is written on the slide and what each visual represents.
2. **Deep-Dive Technical Meaning**: Why each protocol, system, or mechanism was built, how it operates behind the scenes, and relevant RFC/architectural details.
3. **Real-World Analogies**: Explaining the concepts using the instructor's metaphors (e.g., postal letters, phone contact lists, coffee ordering, guards vs. friends).
4. **Midterm Exam Traps & High-Yield Questions**: Specific questions USTH professors commonly ask, common student errors, and key formulas/definitions to memorize.

---

# Section 1: Preview

---

### Slide 1: Title Slide & Context
```text
Web Application Development
Introduction to the Internet and the WWW
KIEU Quoc Viet      HUYNH Vinh Nam
Information and Communication Technology Laboratory (ICTLab),
University of Science and Technology of Hanoi
Hanoi, August 2026 | Lecture 01
```

#### Line-by-Line Breakdown & Meaning
- **"Web Application Development"**: This course is not just about static web design (HTML/CSS). It focuses on building full-stack, dynamic, interactive web software applications (front-end client, back-end server, databases, APIs).
- **"Introduction to the Internet and the WWW"**: The foundational lecture establishing the difference between physical networking infrastructure (Internet) and application-layer software systems (World Wide Web).
- **Academic Context**: Taught at USTH ICTLab. The curriculum bridges computer networking fundamentals with software development.

---

### Slide 2: Table of Contents
```text
Table of Contents
1. Preview
2. How we got here
3. The Internet underneath
4. From Internet to Web
```

#### Line-by-Line Breakdown & Meaning
- **1. Preview**: The high-level view of what happens when a user types a URL in a browser.
- **2. How we got here**: Historical chronology from 1969 to today, explaining why the web was created and how it transitioned from static text documents to complex applications.
- **3. The Internet underneath**: Lower-level networking fundamentals required for web development: Protocols, IP addresses, IPv4 vs. IPv6, NAT, DNS hierarchy, Client-Server model, Firewalls, and Proxies.
- **4. From Internet to Web**: The web-specific technologies: Web pages vs. Sites vs. Web Apps, HTTP requests/responses, HTTP methods, Status codes, URLs, Browsers, Web Servers, Multimedia, Search Engines, and Browser Rendering engines.

---

### Slide 3 & 4: What Happens When You Open a Website? (The 4 Steps)

```text
What happens when you open a website?
You do this dozens of times a day without thinking about it.
This whole course lives in the gap between typing and seeing.
```

#### The Architecture Diagram Explained
The slide presents a circular communication flow between three distinct entities across the Internet:
1. **Your browser** (`usth.edu.vn`)
2. **DNS server**
3. **Web server**

```text
 [Your Browser] ──── (1. which IP?) ─────────────────> [DNS Server]
 [Your Browser] <─── (2. 42.112.24.18) ─────────────── [DNS Server]

 [Your Browser] ──── (3. HTTP request) ──────────────> [Web Server] (via Internet)
 [Your Browser] <─── (4. HTML + CSS + JavaScript) ──── [Web Server] (via Internet)
```

#### Detailed Breakdown of the 4 Steps
1. **Step 1: "1. which IP?" (DNS Query)**
   - The user types a human-readable domain name (e.g., `usth.edu.vn`) into the browser's address bar.
   - Browsers and operating systems do not route network packets using human words; they require numerical IP addresses.
   - The browser queries a **DNS (Domain Name System) server**: *"What IP address corresponds to usth.edu.vn?"*

2. **Step 2: "2. 42.112.24.18" (DNS Response)**
   - The DNS server looks up its records and responds with the server's public IP address: `42.112.24.18`.
   - Now the browser knows the exact destination address on the global Internet.

3. **Step 3: "3. HTTP request" (Client Request)**
   - The browser initiates a TCP connection (handshake) to `42.112.24.18` on port 80 (HTTP) or port 443 (HTTPS).
   - Once connected, the browser formats and sends an **HTTP Request message** (e.g., `GET / HTTP/1.1`).
   - This message travels across physical cables, fiber optics, switches, and routers that constitute **the Internet**.

4. **Step 4: "4. HTML + CSS + JavaScript" (Server Response & Payload)**
   - The remote **Web server** processes the incoming request, locates or generates the requested resources, and packages them into an **HTTP Response message** (e.g., `HTTP/1.1 200 OK`).
   - The payload contains:
     - **HTML**: Structure, semantics, and raw content.
     - **CSS**: Styling, visual rules, layout, typography, colors.
     - **JavaScript**: Client-side logic, interactivity, and dynamic behavior.
   - The browser receives these bytes, parses them, constructs the DOM/CSSOM, and renders pixels onto the screen.

#### Slide Bottom Notes
- **"Four arrows, four topics for today."**: The four arrows represent the DNS resolution phase (Arrows 1 & 2) and the HTTP transaction phase (Arrows 3 & 4).
- **"By the end of this course, you write what comes back in step 4."**: Web developers write the back-end programs that receive Step 3 and dynamically generate/return the code in Step 4.

> **Midterm Exam Tip**:
> If asked: *"What are the exact 4 steps when opening a web page?"*
> 1. DNS Request (Browser asks DNS for IP).
> 2. DNS Response (DNS returns IP address).
> 3. HTTP Request (Browser sends HTTP request to the IP).
> 4. HTTP Response (Server returns HTML, CSS, JS, and media assets).

---

### Slide 5: The Internet Is Not the Web (Road vs. Traffic)

```text
The Internet is not the Web
Most people use these two words as if they mean the same thing.
They are not. One is the road, the other is one kind of traffic on it.
```

#### The Conceptual Architecture
```text
  [ The Web ]       [ Email ]       [ Video Calls ]       [ Online Games ]
  (HTTP / HTTPS)     (SMTP/IMAP)         (WebRTC/RTP)         (Custom UDP/TCP)
  ════════════════════════════════════════════════════════════════════════════
                             THE INTERNET
       Physical cables, fiber, routers, switches, IP addresses (since 1969)
```

#### Detailed Comparison Table from the Slide
| Feature / Concept | The Internet | The Web (World Wide Web) |
| :--- | :--- | :--- |
| **Nature** | The physical network and its rules | One software application built on that network |
| **Function** | Moves raw bytes between two machines | Pages, linked to each other, fetched by a browser |
| **Data Awareness** | Does not care what the bytes mean (content-agnostic) | Understands markup, hyperlinks, documents, and media |
| **Inception Date** | 1969 (ARPANET) | 1990 (Tim Berners-Lee at CERN) — 21 years later! |
| **Analogy** | **The Road System** (asphalt, bridges, traffic lights) | **One type of vehicle/traffic** (e.g., delivery trucks) |
| **Sibling Systems** | Houses the Web, Email, VoIP, P2P, Gaming, SSH, FTP | Sits alongside Email (SMTP), Video calling, Online games |

#### Slide Bottom Note
- **"First half of today: the road. Second half: the traffic you are going to build."**:
  - First half: Network layer, IP addresses, TCP, DNS, routing, NAT, firewalls (The Road).
  - Second half: HTTP protocol, HTML, URLs, web servers, client browsers, dynamic web apps (The Traffic).

> **Midterm Exam Trap**:
> - **Question**: *"Is the World Wide Web synonymous with the Internet?"*
> - **Answer**: **NO**. The Internet is a global network of interconnected computer networks operating at layers 1–4 (Physical, Data Link, Network, Transport). The Web is an application-layer service (Layer 7) that uses HTTP to transfer hypermedia documents across the Internet.

---

# Section 2: How We Got Here (History & Evolution)

---

### Slide 6 & 7: 1969–1989: The Network Before the Web

```text
1969–1989: the network before the web
You already know most of these from your networking course.
What matters here is the order they arrived in.
```

#### The Historical Timeline
- **1969**: **ARPANET links four universities** (UCLA, Stanford Research Institute, UC Santa Barbara, University of Utah).
- **1974**: **TCP/IP becomes the common language** (Specification by Vint Cerf and Bob Kahn).
- **1983**: **DNS invented — names instead of numbers** (Paul Mockapetris; replacing static `HOSTS.TXT`).
- **1989**: **Around 100,000 machines connected** on the network.
- **Key Takeaway**: *"By 1989 the network worked well. There was still nothing to browse."* (No HTML, no HTTP, no hyperlinks, no graphical browsers).

---

### Slide 8 & 9: 1969: Four Computers and One Strange Goal (ARPANET)

```text
1969: four computers and one strange goal
Twenty years before the web, four American universities were wired together.
What they were trying to do explains a lot about how the Internet still behaves.
```

#### 1. "Built to share machines, not to talk"
- **Historical Context**: In 1969, computers (mainframes) cost millions of dollars and filled entire rooms.
- **Original Purpose**: The goal was **remote computation / resource sharing** — allowing a researcher at Utah to run a program on an expensive computer located at UCLA without traveling there.
- **The Accidental Revolution**: **Email** was never part of the original design. Ray Tomlinson invented network email in 1971. Because humans prioritize communication over remote batch computation, email became over 75% of all ARPANET traffic within two years.

#### 2. "Nobody in charge, on purpose" (Decentralization & Survivability)
- **Circuit-Switching vs. Packet-Switching**:
  - Traditional telephone networks used **circuit-switching** (a dedicated physical wire was reserved end-to-end; if the central office was destroyed, all calls dropped).
  - ARPANET pioneered **packet-switching**: Data is chopped into independent **packets**. Each packet contains destination information and independently finds its own route across intermediate nodes (routers/IMPs).
  - If any single node or city is bombed or fails, routers automatically route subsequent packets around the failure.
- **"There is no central computer — which is why nobody can switch the Internet off."**:
  - The Internet is a distributed, peer-to-peer network of autonomous networks. No single server, government, or switch controls the entire system.

#### 3. The Historic Callout: The Network's First Word ("LO")
```text
The first message ever sent was supposed to be LOGIN.
The system crashed after two letters, so the network's first word was LO.
```
- On October 29, 1969, Charley Kline at UCLA attempted to send the command `LOGIN` to the Stanford Research Institute (SRI) computer.
- He typed `L` (SRI confirmed by phone: "Got the L"), then `O` ("Got the O"), and upon typing `G`, the system crashed.
- Thus, the first transmission over the Internet was serendipitously **"LO"** (as in "Lo and behold").

---

### Slide 10–12: 1974: TCP/IP (Addressing vs. Reliable Delivery)

```text
1974: TCP/IP
```

To connect disparate physical networks, Vinton Cerf and Robert Kahn developed the **TCP/IP protocol suite**, dividing network communication into addressing (IP) and transmission control (TCP).

```text
┌────────────────────────────────────────────────────────────────────────┐
│ IP (Internet Protocol) — The Address                                  │
├────────────────────────────────────────────────────────────────────────┤
│ • Every machine on the Internet has its own unique number (IP address).│
│ • IP writes that destination address on each individual packet.        │
│ • Routers inspect the address and forward the packet step-by-step.     │
│ • Connectionless, unreliable, best-effort: IP NEVER checks whether     │
│   the packet actually arrived, nor if packets arrive in order.         │
└────────────────────────────────────────────────────────────────────────┘

┌────────────────────────────────────────────────────────────────────────┐
│ TCP (Transmission Control Protocol) — The Delivery                     │
├────────────────────────────────────────────────────────────────────────┤
│ • Chops large data payloads into small, numbered segments.             │
│ • Tracks sequence numbers; detects lost, duplicate, or corrupted data. │
│ • Automatically requests retransmission of missing packets.            │
│ • Reassembles packets into the exact original order before handing      │
│   the complete stream to the application layer.                        │
└────────────────────────────────────────────────────────────────────────┘
```

#### The Postal Envelope Analogy (Slide Explanation)
- **The Scenario**: Sending a 100-page book through a post office that strictly allows only one single sheet of paper per envelope.
- **Role of IP**: Acts as the address label. IP writes the sender and recipient addresses on the outside of all 100 envelopes so postal trucks can route them.
- **Role of TCP**: Numbers each page (1 to 100) before sealing them. If the recipient receives pages 1–36 and 38–100, TCP spots that **page 37 is missing**, contacts the sender, requests page 37 again, waits for it, and sorts all 100 pages into order before handing the book to the reader.

#### Why This Matters to Web Developers
```text
Your requests travel this way — which is why you will never write code to re-send lost data.
```
- In modern web programming (JavaScript, Node.js, Python), when you write an HTTP request or server handler, the underlying operating system handles TCP.
- You do **not** need to manually check packet loss, calculate checksums, or retransmit lost bytes; TCP abstracts away the network instability and presents a reliable stream.

---

### Slide 13–15: 1983: DNS (Domain Name System)

```text
1983: DNS
```

#### Domain Name vs. DNS Service
1. **Domain Name — The Name**:
   - A short, human-readable text label that people can easily remember (e.g., `usth.edu.vn`, `google.com`).
   - It is purely an abstraction layer for human convenience. **No computer or router on the Internet can be reached with a domain name directly.**
2. **DNS — The Lookup Service**:
   - A globally distributed database of servers that resolves human-readable domain names into the numerical IP addresses required by network hardware.
   - The browser queries DNS *before* initiating any connection to the destination server.

#### The Phone Contact List Analogy
- On a smartphone, you open Contacts, search for "Mum", and tap call.
- The phone looks up the contact record, retrieves the underlying phone number (`+84 912 345 678`), and dials the number over the cellular network.
- You can always bypass the contact book by dialing the raw numbers directly. Similarly, you can type `42.112.24.18` directly into your browser's address bar instead of `usth.edu.vn`.

#### State of the Art by 1989
```text
By 1989 naming, addressing and delivery all worked.
There was still nothing to browse.
```
- Networks had addressing (IP), reliable transport (TCP), and name lookup (DNS).
- What was missing was an open, standardized hypermedia application layer for creating and linking documents across different computer architectures.

---

### Slide 16: 1990: One Person, Three Inventions (Tim Berners-Lee & The Birth of WWW)

```text
1990: one person, three inventions
Tim Berners-Lee, a physicist at CERN, wanted to link research documents together.
In one year he built all three pieces the web still runs on.
```

#### The 3 Foundational Pillars of the Web
In 1989–1990, Sir Tim Berners-Lee at CERN (the European Organization for Nuclear Research) created the three technologies that define the World Wide Web:

```text
        ┌────────────────────────────────────────────────────────┐
        │                  Tim Berners-Lee (1990)                │
        └───────┬───────────────────┬────────────────────┬───────┘
                │                   │                    │
                ▼                   ▼                    ▼
        ┌───────────────┐   ┌───────────────┐   ┌─────────────────┐
        │     HTTP      │   │     HTML      │   │ Browser + Server│
        │  How to ask   │   │  How to write │   │   The first     │
        │ for a document│   │  the document │   │ client and host │
        └───────────────┘   └───────────────┘   └─────────────────┘
```

1. **HTTP (HyperText Transfer Protocol)**: The standardized application-layer protocol defining the grammar for how a client requests a resource and how a server delivers it.
2. **HTML (HyperText Markup Language)**: The standardized document format using tags (`<p>`, `<h1>`, `<a>`) to format text and embed clickable hyperlinks to other documents.
3. **Browser + Server (WorldWideWeb client & CERN httpd server)**: The software implementations demonstrating the concept — the first client program to display hypermedia, and the first host server program to store and serve files over the network.

#### The 1993 Milestone: NCSA Mosaic
```text
In 1993 the Mosaic browser added images inside the page.
That is the moment the web stopped being for researchers.
```
- Prior to 1993, web documents were monochrome text with text-only links; clicking an image link opened a separate external viewer window.
- Marc Andreessen and Eric Bina created the **NCSA Mosaic** browser, introducing the `<img>` tag, allowing graphics to appear **inline** alongside text.
- This transformed the web from an academic research tool into a mass-market multimedia publishing medium.

---

### Slide 17: 1995–Today: From Pages to Applications

```text
1995–today: from pages to applications
The web started as documents you read.
Every step below pushed it closer to software you use.
```

#### The Evolution from Static Documents to Rich Software Applications
```text
 1995                  1998              2005             2007           2014
──┬─────────────────────┬─────────────────┬────────────────┬──────────────┬────────►
  ▼                     ▼                 ▼                ▼              ▼
JavaScript         Server-Side DB       AJAX           Smartphones     HTML5 Standard
Page reacts        Pages generated    Update page      Responsive UI   Native video,
dynamically        from database      without reload   (mobile screens) offline storage
```

1. **1995 — JavaScript**:
   - Created by Brendan Eich at Netscape in 10 days.
   - Allowed the web page to execute logic on the client's machine (form validation, dropdown menus, client-side calculations) without waiting for a server round-trip.
2. **1998 — Server-Side Databases & Dynamic Pages**:
   - Transitioned from static `.html` files stored on disk to pages dynamically generated on-the-fly using programming languages (PHP, Perl, ASP, Java Servlets) backed by relational databases (SQL).
3. **2005 — AJAX (Asynchronous JavaScript and XML)**:
   - Coined by Jesse James Garrett; popularized by Google Maps and Gmail.
   - Allowed JavaScript in the browser to send asynchronous HTTP requests in the background and update specific elements of the DOM **without requiring a full browser page reload**.
4. **2007 — Mobile Web (The iPhone)**:
   - Web browsers moved from desktop monitors to touchscreens.
   - Prompted the development of Responsive Web Design (Media Queries, flexible CSS grid/flexbox layouts) so the same URL functions on desktop and mobile.
5. **2014 — HTML5 Final Recommendation**:
   - Brought native multimedia (`<video>`, `<audio>`), Canvas graphics, Geolocation APIs, WebSockets, LocalStorage, and Service Workers (Progressive Web Apps running offline).
   - Eliminated reliance on third-party binary plugins like Adobe Flash, Microsoft Silverlight, and Java Applets.

#### The Paradigm Shift
```text
Most of what you open in a browser today is not a document at all.
It is an application. Building one is what the rest of this course is about.
```
- A **document** is static content meant for passive reading (e.g., an article, research paper, terms of service).
- An **application** is interactive software executing client-side state transitions, server-side data synchronization, user authorization, and workflows (e.g., Google Docs, Shopee, Netflix, Figma).

---

# Section 3: The Internet Underneath (Core Infrastructure)

---

### Slide 18 & 19: What a Protocol Is (Rules of a Conversation)

```text
What a protocol is
You already know the word from your networking course.
What matters here is how many of them you are going to touch this semester.
```

#### Definition & Core Principles
A **network protocol** is a formal set of agreed-upon rules and conventions governing how two or more entities communicate over a transmission medium.
- It specifies:
  1. **Message Syntax**: What the message looks like (character encoding, headers, delimiting formatting).
  2. **Message Semantics**: What each field, verb, or flag actually means.
  3. **Message Ordering (Sequencing)**: Which side speaks first, when responses are expected, and how errors are handled.
- **Rule of Symmetry**: Both sides must adhere strictly to the identical protocol specification. If one side deviates, communication breaks down.

#### The Real-World Coffee Shop Analogy
```text
Buying coffee: you say the drink, they say the price, you pay, they hand it over.
Swap two steps and it falls apart.
```
- If the barista hands you coffee before you speak, or you pay before asking the price, the transaction fails. Protocol sequencing prevents ambiguity.

#### Protocols Encountered in Web Development
| Protocol | Full Name | Layer | Primary Role |
| :--- | :--- | :--- | :--- |
| **HTTP** | HyperText Transfer Protocol | Application (L7) | Requests and transmits web documents and API payloads. |
| **HTTPS** | HyperText Transfer Protocol Secure | Application + TLS (L7) | HTTP encrypted over TLS/SSL; prevents eavesdropping and tampering. |
| **DNS** | Domain Name System | Application (L7) | Translates human domain names into numerical IP addresses. |
| **TCP** | Transmission Control Protocol | Transport (L4) | Ensures in-order, reliable, error-checked packet delivery. |
| **SMTP** | Simple Mail Transfer Protocol | Application (L7) | Transmits outbound email between mail servers. |

```text
Most of this course is one protocol: HTTP.
Everything else today is there so that HTTP makes sense.
```

---

### Slide 20: What an IP Address Is

```text
What an IP address is
A network finds a device by a number, never by a name.
There are already a few hundred of these numbers in this room.
```

#### Structure of an IPv4 Address
- An **IPv4 address** is a **32-bit binary number** represented in **dotted-decimal notation**:
  - Composed of **four numbers (octets)** separated by dots (e.g., `192.168.1.5`).
  - Each octet contains 8 bits, meaning values range from `0` to `255` ($2^8 = 256$ possible values: 00000000 to 11111111).
  - Assigned dynamically to client devices by a local router via **DHCP (Dynamic Host Configuration Protocol)** when connecting to Wi-Fi/Ethernet. When moving from university Wi-Fi to home Wi-Fi, your device receives a new IP address.

```text
  [Your Laptop] (192.168.1.5) ───┐
                                 ├───> [The Router / Gateway] (192.168.1.1) ───> [The Internet]
  [Your Phone]  (192.168.1.8) ───┘
```

#### Two Special IP Addresses to Memorize for the Midterm
1. **`127.0.0.1` — The Loopback Address ("Localhost")**:
   - Universally points back to the **local machine itself**, on every operating system ever manufactured.
   - Network packets sent to `127.0.0.1` do not leave your computer's network interface card; they loop directly back into the OS networking stack.
   - Crucial for web developers: Allows testing web servers locally without an internet connection or exposing code to outside users.
2. **`192.168.1.1` (or `192.168.0.1`) — The Default Gateway**:
   - The private IP address of your local home/office router on the internal Local Area Network (LAN).
   - Entering this address into a browser accesses the router's administrative web interface.

#### Terminal Commands to View Local IP
- **Windows**: `ipconfig`
- **Linux / macOS**: `ip addr` or `ifconfig`
- *Note*: The IP displayed by `ipconfig` is your private/internal IP, not the public IP seen by web servers on the public Internet.

---

### Slide 21: IPv4 vs. IPv6

```text
IPv4 vs IPv6
Four numbers of 0–255 give about 4.3 billion addresses.
That looked endless in 1981. Our region ran out of free addresses in April 2011.
```

#### Comprehensive Side-by-Side Comparison
| Parameter | IPv4 | IPv6 |
| :--- | :--- | :--- |
| **Example Format** | `42.112.24.18` | `2001:0db8:85a3:0000:0000:8a2e:0370:7334` (or `2001:db8:85a3::8a2e:370:7334`) |
| **Notation** | Four decimal numbers separated by dots (`.`) | Eight groups of 4 hexadecimal digits separated by colons (`:`) |
| **Address Length** | **32 bits** (4 bytes) | **128 bits** (16 bytes) |
| **Total Address Pool** | $2^{32} \approx 4.29 \times 10^9$ (approx. 4.3 billion) | $2^{128} \approx 3.4 \times 10^{38}$ (340 undecillion addresses) |
| **Standardized In** | 1981 (RFC 791) | 1998 (RFC 2460 / RFC 8200) |
| **Primary Advantage** | Short, readable, easy to memorize and type. | Vast address space; every grain of sand on earth can have an IP. |
| **Primary Drawback** | Critically exhausted (APNIC ran out in April 2011). | Long, difficult to memorize; requires network hardware upgrades. |

```text
IPv4 did not disappear — it survives by letting many machines share one address.
That trick is the next slide.
```

---

### Slide 22: Virtual vs. Real IP Address (NAT, Private vs. Public)

```text
Virtual vs real IP address
Virtual - used inside one network only. Starts with 192.168, 10. or 172.16–31
Real - unique on the whole Internet. One per household or office
Search what is my IP - the number you get back is not the one ipconfig
```

#### 1. Private (Virtual) IP Ranges (RFC 1918)
Reserved exclusively for private local area networks (LANs); cannot be routed across the public Internet:
- **`10.0.0.0` to `10.255.255.255`** (`10.0.0.0/8` — 16 million addresses; enterprise networks)
- **`172.16.0.0` to `172.31.255.255`** (`172.16.0.0/12` — 1 million addresses; universities, medium business)
- **`192.168.0.0` to `192.168.255.255`** (`192.168.0.0/16` — 65,536 addresses; home routers)

#### 2. Public (Real) IP Addresses
- Globally unique across the entire worldwide Internet.
- Assigned by ISPs (Internet Service Providers).
- Typically, an entire household or corporate office shares **one single public IP address**.

#### 3. How NAT (Network Address Translation) Works: Request Walkthrough
```text
  [Private Computer]          [Router / NAT Gateway]                [Public Web Server]
    (10.10.0.2)             Private: 10.10.0.1 | Public: 203.162.3.4       (8.8.8.8)
         │                               │                                     │
         ├─── (1) GET Web Page ─────────>│                                     │
         │    Src: 10.10.0.2:54321       │ [Translates & notes in NAT table]   │
         │                               ├─── (2) GET Web Page ───────────────>│
         │                               │    Src: 203.162.3.4:40001           │
         │                               │                                     │
         │                               │<── (3) Returns HTML Page ───────────┤
         │                               │    Dst: 203.162.3.4:40001           │
         │                               │ [Checks NAT table: port 40001]      │
         │<── (4) Passes HTML Page ──────┤                                     │
         │    Dst: 10.10.0.2:54321       │                                     │
```

- **Step 1**: Your laptop (`10.10.0.2`) requests a web page.
- **Step 2**: The router intercepts the packet, crosses out the private source IP (`10.10.0.2`), substitutes its own public IP (`203.162.3.4`), and logs the mapping (including port numbers) in its internal NAT state table.
- **Step 3**: The web server processes the request and sends the response back to `203.162.3.4`. The web server has no idea `10.10.0.2` exists.
- **Step 4**: The router consults its NAT table, identifies that this incoming stream belongs to `10.10.0.2`, translates the destination IP back, and delivers the packets to your laptop.

#### 4. Pros and Cons of NAT (What this buys you, and what it costs)
```text
What this buys you, and what it costs
• Good: One office needs one real address instead of a hundred. This is why IPv4 still works today.
• Cost: Sharing one address means sharing the blame. If one person here misbehaves, a site can block the whole building.
• Good: Nobody outside can reach your computer. It is hidden without you doing anything.
• Cost: That wall works both ways - you cannot host anything either.
```

- **Advantage 1 (Address Conservation)**: Enables thousands of devices on a campus or corporate network to access the Internet using a single public IPv4 address.
- **Advantage 2 (Inbound Privacy / Security)**: Outside computers cannot directly initiate connections into your private IP address; incoming unsolicited packets are dropped by the router.
- **Disadvantage 1 (Shared Reputation / Blacklisting)**: If a single infected computer or malicious actor on your Wi-Fi network spams a service, the external website blocks the public IP (`203.162.3.4`), blocking every user in the building.
- **Disadvantage 2 (Hosting Barriers)**: You cannot easily host a public website on your laptop from home without configuring router **Port Forwarding** or using tunneling services (e.g., ngrok, Cloudflare Tunnels).

---

### Slide 23: Domain Names and DNS in Practice

```text
Domain names and DNS
A browser cannot use a name. It needs a number.
So before asking for the page, it has to ask someone else for the number.
```

#### Step-by-Step Flow: You type `vnexpress.net`
```text
  [Client Browser]                                  [DNS Server]                     [Web Server]
        │                                                │                                │
        ├─── 1. "What is the IP for vnexpress.net?" ────>│                                │
        │<── 2. "111.65.248.132" ────────────────────────┤                                │
        │                                                                                 │
        ├─── 3. "GET / HTTP/1.1" ────────────────────────────────────────────────────────>│
        │<── 4. "HTTP/1.1 200 OK (HTML bytes)" ───────────────────────────────────────────┤
```

#### "Two machines, two jobs"
- **The DNS Server**: Does **not** store or serve website content. It only provides IP address lookup directions (like a telephone operator).
- **The Web Server**: Stores and serves the actual website files (HTML, CSS, images).
- **Performance Implication**: *"A slow DNS server makes every site feel slow, even a perfect one."* Because DNS lookup precedes the HTTP connection, high DNS latency delays initial page rendering even if the web server has sub-millisecond response times.

---

### Slide 24: The DNS Tree (Hierarchical Resolution)

```text
The DNS tree
No single machine could hold every name on the Internet.
So names are split into levels, and each level only knows about the one below it.
```

#### The Hierarchical Tree Structure
```text
                          [ "." (Root Domain) ]
                                    │
       ┌──────────────┬─────────────┼─────────────┬──────────────┐
     .com           .edu          .gov          .org           .vn (ccTLD)
       │              │                                          │
   microsoft       harvard                                     edu.vn
       │                                                         │
     sales                                                     usth.edu.vn
       │                                                         │
 Computer1.sales.microsoft.com                             mail.usth.edu.vn
```

#### Reading a Domain Name: Always from Right to Left!
Using `mail.usth.edu.vn`:
1. **`vn` (Country Code Top-Level Domain - ccTLD)**: Managed by Vietnam Internet Network Information Center (VNNIC).
2. **`edu.vn` (Second-Level Domain under `.vn`)**: Designated for educational institutions in Vietnam.
3. **`usth.edu.vn` (Registered Domain)**: Registered by the University of Science and Technology of Hanoi under `edu.vn`.
4. **`mail.usth.edu.vn` (Subdomain / Specific Host)**: USTH controls this subdomain internally without requiring permission from VNNIC.

#### Why DNS is Built as a Distributed Tree
1. **Delegation of Authority**: Each server level only needs to know the IP addresses of the authoritative name servers one tier below it.
2. **Scalability & Autonomy**: When USTH creates a new subdomain (`portal.usth.edu.vn` or `moodle.usth.edu.vn`), it updates its own DNS records without needing to contact national or global registrars.

---

### Slide 25: Client and Server Architecture

```text
Client and server
These are not two kinds of computer. They are two roles in one conversation.
The role is decided by who speaks first.
```

```text
                      ┌───────────────┐
                      │    Network    │
                      └───────┬───────┘
                              │
  [ Client ] ─── (Request) ───┼───> [ Server ]
  [ Client ] <── (Response) ──┴──── [ Server ]
```

#### Client vs. Server: Core Operational Differences
| Attribute | Client | Server |
| :--- | :--- | :--- |
| **Initiative** | **Starts every conversation.** Never passive. | **Never speaks first.** Passively listens. |
| **Operational Lifecycle** | Sends request, waits for response, then usually stops. | Runs continuously (daemon/service); serves thousands of concurrent clients. |
| **Address Requirement** | Can have a temporary, private, dynamic IP behind NAT. | Requires a predictable, permanent, public IP or routable domain name. |
| **Examples** | Web browser, mobile application, CLI tool (`curl`). | Node.js, Apache HTTP Server, Nginx, Express server. |

#### Local Development in the Lab
```text
In the lab your laptop plays both roles:
a server program answering on 127.0.0.1, and a browser asking it.
That is why you can build a whole web site before putting anything online.
```
- Your development computer runs both the client (Chrome) and the server (Node.js/Express) simultaneously.
- Chrome sends an HTTP request to `http://127.0.0.1:3000/`, which loops back within the OS directly to the Node.js server process.

---

### Slide 26: Firewall and Proxy

```text
Firewall and proxy
Both sit between you and the Internet, and both look the same in a diagram.
But one stops messages, and the other carries them for you.
```

```text
                       FIREWALL ("The Guard at the Door")
 [Internal LAN] ───► [ Firewall ] ───X─── [ Malicious Actor / Unauthorized Traffic ]
                     (Inspects & Blocks)

                          PROXY ("The Friend You Send")
 [Internal LAN] ───► [ Proxy Server ] ───────► [ Destination Web Server ]
                     (Fetches on your behalf; caches responses)
```

#### Comparison Table from Slide
| Dimension | Firewall ("The Guard at the Door") | Proxy ("The Friend You Send") |
| :--- | :--- | :--- |
| **Primary Job** | **Inspects and filters.** Lets through only authorized traffic; drops unauthorized packets. | **Acts as intermediary.** You ask the proxy, the proxy fetches from the target, and hands it back. |
| **Core Question Answered** | **"Is this allowed?"** | **"Who is doing the asking?"** |
| **Primary Benefit** | Prevents cyberattacks, port scans, and unauthorized protocol access. | Hides client identity; **caches** popular resources to speed up page loads. |
| **Trade-offs / Costs** | Can accidentally block legitimate developer tools or server ports. | Potential bottleneck; risk of caching stale data or intermediate attacks. |

---

# Section 4: From Internet to Web (Web Technologies & Protocols)

---

### Slide 27 & 28: Page, Site, Application

```text
Page, site, application
```

#### The Three Evolutionary Stages
```text
  [ A Web Page ]          ───►          [ A Web Site ]          ───►        [ A Web Application ]
  • One single document                 • Related pages under                • A site where you do work
  • E.g., one news article                one common domain                  • E.g., Gmail, Shopee,
                                        • E.g., all of vnexpress.net           Online Banking
```

#### Detailed Comparison: Reading a Page vs. Using an Application
| Characteristic | On a Page You Read (Web Page) | In an Application You Use (Web App) |
| :--- | :--- | :--- |
| **Interaction** | Passive: Open, scroll, read, leave. | Active: Authenticate, fill forms, trigger workflows, purchase. |
| **State & Persistence** | **Stateless**: Nothing you do is remembered. Returning tomorrow yields the exact same page with no memory of your visit. | **Stateful**: Actions are committed to a server-side database. Open Gmail tomorrow, and emails/drafts persist. |
| **Data Flow** | Unidirectional: Server $\rightarrow$ Client. | Bidirectional: Client $\leftrightarrow$ Server continuous sync via APIs/AJAX. |

---

### Slide 29: HTTP and HTML (Transport vs. Content)

```text
HTTP and HTML
```

#### Side-by-Side Breakdown
```text
┌───────────────────────────────────────────────────┐  ┌───────────────────────────────────────────────────┐
│ HTML — HyperText Markup Language                  │  │ HTTP — HyperText Transfer Protocol                │
├───────────────────────────────────────────────────┤  ├───────────────────────────────────────────────────┤
│ Example Code:                                     │  │ Example Code:                                     │
│   <h1>Course list</h1>                            │  │   GET /courses HTTP/1.1                           │
│   <p>Web Application Development</p>              │  │   Host: usth.edu.vn                               │
│                                                   │  │                                                   │
│ • A language for writing the document.            │  │ • A set of rules for moving the document.         │
│ • Tags wrap content to declare semantic roles:    │  │ • Rules governing conversation between client     │
│   headings, paragraphs, links, tables, lists.     │  │   and server.                                     │
│ • YOU WRITE THIS. This is the visual structure.   │  │ • YOU DO NOT WRITE THIS directly. The browser     │
│                                                   │  │   and server engines generate and parse this.     │
└───────────────────────────────────────────────────┘  └───────────────────────────────────────────────────┘
```

#### Encapsulation Relationship
```text
  HTTP Response Message
  ┌──────────────────────────────────────────────┐
  │ HTTP/1.1 200 OK                              │
  │ Content-Type: text/html                      │
  │                                              │
  │ ┌──────────────────────────────────────────┐ │
  │ │ <h1>Course list</h1>                     │ │ <── The HTML document is encapsulated
  │ │ <p>Web Application Development</p>       │ │     inside the body of the HTTP response.
  │ └──────────────────────────────────────────┘ │
  └──────────────────────────────────────────────┘
```
- **Historical Note**: Created by the same person (Tim Berners-Lee) in the same year (1990).

---

### Slide 30: One HTTP Conversation (Detailed Syntax of Request & Response)

```text
One HTTP conversation
```

#### 1. Anatomy of an HTTP Request
```http
GET /courses/web HTTP/1.1
Host: usth.edu.vn
```
- **Line 1: The Request Line (3 components)**:
  1. `GET`: The **HTTP Method (Verb)** declaring the action requested (*"fetch me something"*).
  2. `/courses/web`: The **Request Target / Path** identifying the specific resource on the server.
  3. `HTTP/1.1`: The **Protocol Version** being utilized.
- **Line 2: The `Host` Header**:
  - `Host: usth.edu.vn`: Identifies the exact domain name requested.
  - **Why the Host header is required in HTTP/1.1**: A single physical web server with one IP address often hosts dozens of different websites (known as **Virtual Hosting** or multi-tenancy). The server inspects the `Host` header to route the request to the correct site configuration.

#### 2. Anatomy of an HTTP Response
```http
HTTP/1.1 200 OK
Content-Type: text/html

<h1>Course list</h1>
```
- **Line 1: The Status Line (3 components)**:
  1. `HTTP/1.1`: The protocol version.
  2. `200`: The **Status Code** (numerical status: *"Found it / Success"*).
  3. `OK`: The **Reason Phrase** (human-readable explanation).
- **Line 2: Response Headers**:
  - `Content-Type: text/html`: The **MIME Type** header informing the browser how to interpret the payload bytes (as an HTML page, JPEG image, JSON object, etc.).
- **Line 3: Mandatory Empty Line (`CRLF` — Carriage Return + Line Feed)**:
  - Critical protocol requirement: Separates HTTP metadata headers from the response body.
- **Line 4+: The Message Body (Payload)**:
  - The actual HTML, CSS, JSON, or binary data requested.

#### 3. Backward Compatibility & Architectural Longevity
```text
These two shapes were fixed in 1990 and never changed.
Chrome, released in 2008, can fetch a page from a server program written before Chrome existed.
```
- Because HTTP is an open, text-based standard with strict backward compatibility, modern browsers can seamlessly communicate with legacy HTTP servers.

---

### Slide 31: Two Words in Every Conversation: Methods & Status Codes

```text
Two words in every conversation
```

#### Part 1: The HTTP Methods (Verbs) — What You Want Done
Every HTTP request begins with an HTTP verb indicating the desired action:

| HTTP Method | Primary Purpose | Real-World Web Action | Relational Database (SQL / CRUD) Equivalent |
| :--- | :--- | :--- | :--- |
| **GET** | Retrieve / read a resource | Opening any page or clicking a hyperlink | **SELECT** (Read) |
| **POST** | Submit data / create new resource | Submitting a form or clicking "Sign Up" | **INSERT** (Create) |
| **PUT** | Replace / overwrite existing resource | Updating profile details or editing a post | **UPDATE** (Replace) |
| **DELETE** | Remove an existing resource | Deleting a photo or deleting a comment | **DELETE** (Remove) |

---

#### Part 2: The HTTP Status Codes — How It Went
Every HTTP response returns a 3-digit status code divided into functional blocks:

| Status Code Range | Category | Meaning & Responsibility |
| :--- | :--- | :--- |
| **`1xx`** | Informational | Request received, continuing process. |
| **`2xx`** | Success | The action was successfully received, understood, and accepted. |
| **`3xx`** | Redirection | Further action must be taken to complete the request. |
| **`4xx`** | Client Error | The error was caused by the client (invalid syntax, bad URL, unauthenticated). |
| **`5xx`** | Server Error | The server failed to fulfill an apparently valid request (program crash, overload). |

#### Specific Status Codes Covered on the Slide (Must Memorize for Midterm!)
- **`200 OK`**: Standard success response. The requested resource is in the response body.
- **`201 Created`**: The request succeeded and a new resource was created on the server (common after POST sign-up).
- **`301 Moved Permanently`**: The URL of the requested resource has been changed permanently; browser redirects automatically.
- **`304 Not Modified`**: Caching optimization. The resource has not changed since the last request; the browser uses its local cached copy without re-downloading bytes.
- **`400 Bad Request`**: The server cannot understand the request due to malformed syntax.
- **`401 Unauthorized`**: Authentication is required. You must log in before accessing this resource.
- **`403 Forbidden`**: Authorization failure. The server understood who you are, but you do not have permission to view this resource.
- **`404 Not Found`**: The server cannot find the requested URL path.
- **`500 Internal Server Error`**: The server code crashed or threw an unhandled exception.
- **`503 Service Unavailable`**: The server is temporarily overloaded or down for maintenance.

#### The Golden Rule for Debugging (Exam Favorite!)
```text
  4xx ──► Look at my request (The client made a mistake)
  5xx ──► Look at the server  (The server crashed or threw an exception)
```
- *"The one you will see most this term: 500 — and the program that crashed will be yours."*

---

### Slide 32: Web Client: The Browser

```text
Web client: the browser
In every conversation we have drawn today, the client is your web browser.
Chrome, Safari, Edge, Firefox, Opera, Coc Coc - all of them send the same GET line.
```

#### 1. What the Web Browser Program Does
1. Formats and dispatches HTTP requests (e.g., `GET /index.html`) over TCP/IP.
2. Receives and parses the returning HTTP response and HTML payload.
3. Constructs the **DOM (Document Object Model)** tree and **CSSOM (CSS Object Model)** tree.
4. Identifies dependent assets (images, stylesheets, fonts, scripts) referenced in the HTML and issues secondary GET requests.
5. Paints the rendered pixels onto the screen.

#### 2. Developer Tools Inspection (Hands-On Lab)
```text
Press F12, open the Network tab, reload the page.
Every request from the last slide is listed there:
the path, the 200 or 404, and what came back.
```
- Opening browser DevTools (F12) reveals every HTTP transaction in real time: request method, URL path, response status code, content size, and download timing waterfall.

---

### Slide 33: Web Server

```text
Web server
A web server is a program, not a machine.
Apache, Nginx, Internet Information Services, Node.js - you install one, the way you install any program.
```

#### 1. Software vs. Hardware Distinction
- In colloquial English, people refer to the metal machine in a data center as a "server".
- In computer science, a **web server is software** — a background daemon process that binds to a network socket (port 80 or 443) and listens for incoming HTTP requests.

#### 2. What the Web Server Program Does
- **Waits**: It remains idle, listening on a port. It **never initiates communication**.
- **Inspects**: When a request arrives, it parses the HTTP method and URL path.
- **Fulfills or Rejects**:
  - If a file exists at the requested path, or an API route matches, it reads the data and returns `200 OK`.
  - If no matching resource exists, it generates an error response: `404 Not Found`.

#### 3. Running a Web Server in Lab 1
```text
Install Node.js on your laptop and your laptop is a web server.
Open 127.0.0.1 in Chrome and your laptop is also the client.
```
- Running Node.js turns your local machine into a web server host. Browsing `http://127.0.0.1/` connects your local browser directly to your local Node process.

---

### Slide 34: Anatomy of a URL

```text
Anatomy of a URL
A URL is not one thing. It is four answers to four different questions,
glued together and typed into one box.
```

#### Comprehensive Component Breakdown
```text
   https://        usth.edu.vn         /courses/web         ?year=2026
  └────────┘      └───────────┘       └────────────┘       └───────────┘
   [Scheme]          [Host]               [Path]              [Query]
 Which protocol?  Which machine?    Which resource?      Extra parameters
```

| URL Component | Example | Role / Question Answered | Who Decided It? |
| :--- | :--- | :--- | :--- |
| **Scheme** | `https://` | Declares the communication protocol to use. | **Decided for you** (Global IETF/W3C standard). |
| **Host** | `usth.edu.vn` | Identifies which physical/virtual server to contact. | **Decided for you** (Registered domain via DNS). |
| **Path** | `/courses/web` | Identifies which specific page/endpoint to access. | **Decided by YOU** (The web developer). |
| **Query String**| `?year=2026` | Carries key-value pairs (`key=val`) providing parameters (filters, pagination, search). | **Decided by YOU** (The web developer). |

> **Midterm Detail**: Note that URL paths and query strings are created arbitrarily by web developers. There is no technical requirement that `/courses` must exist on a server; the developer writes the route handler that interprets that string.

---

### Slide 35: Home Page, Hyperlink, Tab

```text
Home page, hyperlink, tab
```

```text
                     ┌───► [ News ] ───► [ One Article ]
  [ Home Page ] ─────┤
                     └───► [ Courses ] ───► [ Web Dev ]
```

#### 1. Hyperlinks (`<a>` Anchor Tag)
- A hyperlink is created via HTML:
  ```html
  <a href="/courses">See all courses</a>
  ```
- **Mechanism**: When a user clicks the anchor text, the browser reads the `href` attribute, constructs an HTTP request: `GET /courses HTTP/1.1`, sends it to the server, and renders the incoming response. Hyperlinks interconnect the World Wide Web.

#### 2. The Home Page
- Requesting a domain with no trailing path (e.g., `https://usth.edu.vn/`) prompts the web server to return the default entry-point file (conventionally `index.html`).
- The home page serves as the root hub from which all other pages are linked.

#### 3. Browser Tabs & Concurrency
```text
Ten tabs means ten separate conversations, with ten different servers, at the same time.
```
- Each browser tab maintains its own independent network sockets, rendering contexts, DOM instances, and JavaScript execution threads.

---

### Slide 36: Web Multimedia

```text
Web multimedia
A page is not only text. The same GET request can bring back a song, a film or a map.
The Content-Type line tells the browser which one is arriving.
```

#### 1. Multimedia Types & Examples
- **Audio**: Spotify streaming music inside a tab (MIME: `audio/mpeg`, `audio/ogg`).
- **Video**: YouTube video playback (MIME: `video/mp4`, `video/webm`).
- **Animation**: CSS animations, SVG transforms, or loading spinners.
- **3D Graphics**: WebGL / Three.js 3D building models in Google Maps.

#### 2. Native Multimedia in HTML5
```html
<video src="lecture.mp4" controls>
</video>
```
- **Historical Significance**:
  - **Before HTML5**: Browsers could not decode video natively. Users were forced to download and install proprietary binary plugins (Adobe Flash, Apple QuickTime, Microsoft Silverlight). These plugins were notorious security vulnerabilities and caused frequent browser crashes.
  - **After HTML5**: Browsers feature native hardware-accelerated video decoding directly via the `<video>` element with zero third-party software required.

---

### Slide 37: Search Engines & Web Crawlers

```text
Search engines
Google, Bing, Coc Coc - programs that find pages on the WWW for you.
They find them the same way you do: by following links.
```

```text
  [ Google Crawler ] ───► [ Known Page A ] ───(a href)───► [ Your Page B ]      [ Orphan Page C ]
                                                                                (No incoming links)
                                                                                  "NEVER FOUND"
```

#### 1. How Web Crawlers (Spiders / Bots) Work
1. Automated indexing programs (e.g., Googlebot) fetch known seed web pages via HTTP `GET` requests.
2. The crawler parses the HTML, extracts every `<a href="...">` link, and appends those URLs to its queue.
3. The crawler issues `GET` requests to all discovered URLs, repeating this recursive cycle continuously across the global web.

#### 2. Search Engine Optimization (SEO) Implications
- **Orphan Pages**: If no other page on the Internet contains a hyperlink linking to your page, search engine crawlers will never discover it.
- Hyperlinks serve two equal purposes: They allow human users to navigate between pages, and they allow search engine crawlers to discover and index websites.

---

### Slide 38: What a Browser Actually Does (The 4 Engine Phases)

```text
What a browser actually does
A browser is not a window. It is a program that does four jobs every time you open a page.
Three of them you never see.
```

```text
  ┌──────────────┐     ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
  │   1. ASK     │ ──► │   2. READ    │ ──► │   3. DRAW    │ ──► │    4. RUN    │
  │ Send request,│     │ Work out what│     │ Turn that    │     │ Execute the  │
  │ wait answer  │     │ HTML describes│    │ into pixels  │     │  JavaScript  │
  └──────────────┘     └──────────────┘     └──────────────┘     └──────────────┘
```

#### Detailed Breakdown of the 4 Internal Phases
1. **Phase 1: ASK (Network Request)**:
   - Formats the HTTP request, sends it over TCP/IP, and waits for server response bytes.
2. **Phase 2: READ (Parsing & Tree Construction)**:
   - Parses incoming HTML tokens to build the **DOM (Document Object Model)** tree.
   - Parses CSS rules to build the **CSSOM (CSS Object Model)** tree.
3. **Phase 3: DRAW (Layout, Render Tree & Painting)**:
   - Merges DOM + CSSOM into a **Render Tree**. Computes geometric layout coordinates for every box, then rasterizes/paints pixels onto the screen.
4. **Phase 4: RUN (JavaScript Execution Engine)**:
   - The browser's JavaScript engine (e.g., V8 in Chrome, SpiderMonkey in Firefox) executes scripts.
   - Scripts can dynamically mutate the DOM, respond to user events, and fetch background data.

#### Key Observation 1: "One page is not one request"
- The initial HTTP response contains only the HTML document.
- As the parser reads the HTML, it discovers references to external resources (`<img src="...">`, `<link rel="stylesheet">`, `<script src="...">`).
- The browser dispatches separate, parallel HTTP GET requests for each asset.
- **Exam Rule of Thumb**: Loading a modern web page typically triggers **50 to 100 individual HTTP requests**.

#### Key Observation 2: "Step 4 is unusual"
```text
Once drawn, the JavaScript keeps running and can ask for more, with no reload.
That is the whole difference between a page you read and an application you use.
```
- In static web pages, the browser's work completes after Step 3.
- In modern web applications, Step 4 never terminates. JavaScript remains active in the background, listening for user interactions, dispatching background AJAX/Fetch requests, and modifying the DOM dynamically without reloading the page.

---

### Slide 39: Conclusion

```text
Thank you for listening!
Scan for the session evaluation!
Lecture 01 | Hanoi, August 2026 | 34 / 34
```
- Concludes Lecture 01.

---

# Midterm Exam Master Review: Key Differences, Traps & Exam Questions

This section compiles high-yield summary tables, common midterm traps, and practice exam questions covering all concepts in Lecture 01.

---

### 1. High-Yield Comparison Tables

#### A. Internet vs. Web
| Dimension | The Internet | The World Wide Web |
| :--- | :--- | :--- |
| **Layer** | Physical, Data Link, Network, Transport (Layers 1–4) | Application Layer (Layer 7) |
| **Function** | Physical and logical transmission of raw bytes | Hyperlinked documents and software applications |
| **Year Invented**| 1969 (ARPANET) | 1990 (Tim Berners-Lee) |
| **Primary Protocols**| IP, TCP, UDP, BGP | HTTP, HTTPS, WebSocket |

#### B. TCP vs. IP
| Feature | IP (Internet Protocol) | TCP (Transmission Control Protocol) |
| :--- | :--- | :--- |
| **Primary Responsibility**| Addressing and packet routing | Reliable delivery and sequencing |
| **Reliability** | Unreliable (Best-effort delivery) | 100% Reliable (Retransmits lost packets) |
| **Packet Awareness** | Treats every packet independently | Numbers packets and reassembles them in order |

#### C. Firewall vs. Proxy
| Question | Firewall | Proxy Server |
| :--- | :--- | :--- |
| **Core Question** | *"Is this traffic allowed through?"* | *"Who is asking for this resource?"* |
| **Action** | Blocks unauthorized ports/IPs/packets | Fetches data on behalf of client; caches pages |
| **Visibility** | Acts as an active filter/gate | Acts as an intermediary front-man |

#### D. 4xx vs. 5xx Status Codes
| Code Class | Error Name | Who is at Fault? | Where do you look to fix it? |
| :--- | :--- | :--- | :--- |
| **`4xx`** | Client Error (e.g., 400, 401, 403, 404) | The Client (Browser/Developer request) | Inspect the client code, URL, headers, authentication |
| **`5xx`** | Server Error (e.g., 500, 503) | The Server (Back-end program crash) | Inspect server-side error logs and crash dumps |

---

### 2. Common Midterm Traps & Misconceptions

1. **Trap: "A web server is an expensive computer in a server rack."**
   - **Correction**: A web server is **software** (e.g., Apache, Nginx, Node.js). Any computer (including your laptop) becomes a web server when running web server software.
2. **Trap: "DNS stores and returns the HTML code of the website."**
   - **Correction**: DNS **never** sees or stores website content. DNS only resolves domain names into IP addresses.
3. **Trap: "Typing a URL results in exactly one HTTP request."**
   - **Correction**: The initial request fetches only the HTML. Every image, CSS stylesheet, font, and JavaScript file referenced inside that HTML requires its own separate HTTP GET request (50–100 requests per page load).
4. **Trap: "401 Unauthorized and 403 Forbidden are identical."**
   - **Correction**: `401 Unauthorized` means the user is **not authenticated** (not logged in; identity unknown). `403 Forbidden` means the user is authenticated, but **lacks authorization/permission** to access the resource.
5. **Trap: "IPv4 ran out of addresses, so computers can no longer use it."**
   - **Correction**: IPv4 continues to function worldwide due to **NAT (Network Address Translation)**, which allows thousands of private devices to share a single public IPv4 address.
6. **Trap: "Web developers must write code to handle dropped packets."**
   - **Correction**: TCP operates at the transport layer below HTTP and handles packet retransmission automatically. Web developers work at the application layer and receive an error-checked byte stream.

---

### 3. Practice Midterm Exam Questions & Solutions

#### Question 1 (Short Answer)
**Explain the exact difference between `127.0.0.1` and `192.168.1.1`.**
> **Answer**: `127.0.0.1` is the loopback IP address representing the local machine itself ("localhost"), enabling programs on a computer to communicate internally without leaving the network card. `192.168.1.1` is a private IP address representing the default gateway (the local router), used to access the router's management settings.

#### Question 2 (Scenario Analysis)
**A user opens Chrome and navigates to `https://shop.vn/products?cat=books`. Identify the 4 components of this URL and specify which were decided by internet standards vs. the site developer.**
> **Answer**:
> - Scheme: `https://` (Decided by internet standards)
> - Host: `shop.vn` (Decided by domain registration via DNS)
> - Path: `/products` (Decided by the web developer)
> - Query string: `?cat=books` (Decided by the web developer)

#### Question 3 (Networking & NAT)
**Why does running `ipconfig` on your laptop display `192.168.1.45`, but visiting `whatismyip.com` displays `118.70.12.190`? Explain the mechanism responsible.**
> **Answer**: `192.168.1.45` is a private (virtual) IP address assigned to the laptop by the local router via DHCP for use within the local network. `118.70.12.190` is the single public IP address assigned to the router by the ISP. The mechanism responsible is **NAT (Network Address Translation)**, which replaces private source IPs with the router's public IP when sending packets out to the public Internet.

#### Question 4 (HTTP Protocols)
**In an HTTP request, what is the purpose of the `Host:` header, and why was it made mandatory in HTTP/1.1?**
> **Answer**: The `Host:` header specifies the domain name of the website the client wishes to reach. It was made mandatory in HTTP/1.1 to support **Virtual Hosting**, where a single physical server with a single IP address hosts multiple websites. Without the `Host:` header, the server cannot determine which website's files to serve.

#### Question 5 (Browser Architecture)
**List the four internal phases a web browser executes when opening a web page. Which phase distinguishes a modern web application from a traditional static document?**
> **Answer**:
> 1. **Ask** (Send HTTP request, wait for response)
> 2. **Read** (Parse HTML/CSS to build DOM and CSSOM)
> 3. **Draw** (Calculate layout, construct render tree, paint pixels)
> 4. **Run** (Execute JavaScript engine)
>
> **Phase 4 (Run)** distinguishes a web application from a static document: In an application, JavaScript continues running after initial paint, handling client-side state, user actions, and background network requests without page reloads.
