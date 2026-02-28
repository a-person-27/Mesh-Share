What is Mesh Share?
Mesh Share is a lightweight, serverless file-sharing desktop app that lets devices on the same local network discover each other automatically and exchange files — no cloud, no accounts, no setup.

Built with Python, Tkinter, and Zeroconf (mDNS), it turns your LAN into a simple mesh of shareable folders.

Features
Auto-Discovery — Peers are found automatically via mDNS/Zeroconf. No IP addresses to type.
Drag & Drop — Drop files directly into the app to start sharing them.
Browse & Download — Double-click a peer to see their shared files, double-click a file to download it.
Progress Tracking — Real-time progress bar for file transfers.
No Server — Fully peer-to-peer. Every instance is both a client and a server.
Cross-Platform — Works on Windows, macOS, and Linux.
Quick Start
Prerequisites
pip install zeroconf tkinterdnd2
Run
python meshshare.py
That's it. The app will open, register itself on the network, and start discovering other Mesh Share instances automatically.

How It Works
On launch, a TCP server starts on a random high port.
The app registers itself as a _meshshare._tcp.local. service via Zeroconf.
Other Mesh Share instances on the LAN discover it automatically.
Peers exchange file listings and transfer files over raw TCP sockets.
Usage
Action	How
Share files	Click Add Files / Add Folder, or drag & drop onto the window
Browse a peer	Double-click a name in the Peers panel
Download a file	Double-click a file in the Peer Files panel
Remove a shared file	Select it and click Delete Selected
Project Structure
mesh-share/
├── meshshare.py     # Main application
├── shared/          # Auto-created shared folder
├── logo.jpg         # App logo
└── README.md
Contributing
Pull requests are welcome! If you'd like to add features like encryption, folder sync, or a mobile client, feel free to open an issue first to discuss.
