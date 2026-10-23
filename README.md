BotVPN

A single-port VLESS VPN server and web dashboard written in pure Python (asyncio). Built for bot/game hosting panels (Pterodactyl, Bot-Hosting, KataBump, Nexcloud, etc.) and Linux VPS setups where you only get 1 port, no root access, and no tun driver.

Features

Single-Port Multiplexer: Runs VLESS TCP-REALITY, VLESS Raw-TCP, WebSocket, Subscription feeds, and the Web Dashboard on the exact same port.

Works in Iran, China & Russia: Includes a pure-Python TLS 1.3 X25519 REALITY handshake + smart DPI packet splitting + built-in port-53 UDP-over-TCP DNS resolution (fixes Windows v2rayN TUN mode DNS timeouts).

Auto-Detects IP, Domain & Port: Automatically detects your server's public IPv4, node hostname/domain, and port from panel environment variables (SERVER_PORT, PORT, PUBLIC_PORT, APP_PORT) and your browser's URL bar.

Zero-Error HTTPS Subscriptions: Automatically publishes a CA-signed Port-443 https:// subscription mirror so strict apps (Happ, v2rayNG, v2rayN, NPV Tunnel) never complain about self-signed certificates or non-443 ports.

Step-by-Step Setup Guide

1. Bot / Game Hosting Panels (Pterodactyl, Bot-Hosting, KataBump, etc.)

Upload the files: Upload botvpn.zip to your server's file manager and click Unarchive / Extract (so main.py, tcp_relay.py, pages.py, etc. are in the root folder).

Startup File: Make sure your panel's startup file is set to main.py (we also included app.py, bot.py, and index.py wrappers in case your host requires one of those names).

Start the server: Click Start. In the console, you'll see:

[BotVPN v25.0.0] Running on 0.0.0.0:PORT -> Panel: http://YOUR_HOST:PORT/login (Default login: admin / admin)


Log into the Dashboard:

Open http://YOUR_HOST:PORT/login in your browser.

Default username: admin

Default password: admin (you can change this in the Settings tab).

Connect:

Click Copy REALITY or Copy Raw-TCP to paste a single config directly into NPV Tunnel, Happ, v2rayN, or v2rayNG.

Click Copy Sub to copy the Port-443 https:// subscription link for Happ, v2rayNG, or v2rayN.
