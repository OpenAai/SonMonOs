# SonMonOs

**Sonos Multicast Monitor for Ubuntu**  
Monitor Sonos multicast and network activity in real time using an Ubuntu-based server, tcpdump, and a lightweight web interface.

## 🌐 Purpose

SonMonOs helps users detect Sonos speaker network issues, such as dropouts caused by multicast/IGMP problems. It provides insight through a clean web interface with per-speaker status.

## 🔍 What do we monitor?

* Multicast traffic to and from Sonos devices
* IGMP Join/Leave/Query behavior
* mDNS (Bonjour) traffic from Sonos and other devices
* UPnP/SSDP announcements
* Sonos-specific anomalies like silent disconnects

## 📡 Network Protocols

* IGMP (Internet Group Management Protocol)
* UDP Multicast
* mDNS (UDP 5353)
* SSDP (UDP 1900)

## 📦 TCP/UDP Ports

* UDP 1900 (SSDP)
* UDP 5353 (mDNS)
* UDP 6969 (used by tools like `mcjoin`)
* Dynamic ports from Sonos devices

## 🖥️ Web Interface

The web page displays:

* 📶 Per-device Sonos status (e.g., active, no traffic, dropout)
* ⏱️ Last activity timestamp
* 🌍 IP address and multicast group info
* 🕵️‍♂️ Dropout or anomaly alerts

Built with:

* `lighttpd` or `python3 -m http.server`
* HTML/JS front-end with `fetch()` for JSON updates
* Backend script generates real-time status from `tcpdump` logs

## 🚨 Alerts (Optional)

* 📧 Email or 📱 Signal alerts for dropouts or IGMP issues
* Pluggable alert system: easy to extend

## 🧠 Future Ideas

* 📈 Graphs showing per-speaker traffic
* 🧪 Detection of multiple IGMP queriers or STP loops
* 🛠️ UniFi controller API integration
* ☁️ Logging to centralized systems (e.g., InfluxDB + Grafana)

## 💻 Project Structure

* sonmonos/
  * web/
    * index.html
    * style.css
    * status.json (generated)
  * scripts/
    * multicast-monitor.sh
    * generate-status.py
  * systemd/
    * multicast-monitor.service
  * README.md
  * LICENSE


## 🚀 Installation (coming soon)

## 📢 Community

SonMonOs will be shared with the Ubiquiti and Sonos communities as a reference project for network debugging.

---

**Author**: OpenAai (GitHub: [OpenAai](https://github.com/OpenAai))  
**Project Status**: 🚧 In development  
**Feedback and contributions are welcome!
