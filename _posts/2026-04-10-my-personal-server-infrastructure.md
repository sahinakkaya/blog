---
title: "My Personal Server Infrastructure: A Project I'm Proud Of"
date: 2026-04-10 14:30:00 +0300
tags: self-hosting infrastructure server homelab docker automation
classes: wide
excerpt: "How I built a comprehensive personal server infrastructure with automated deployments, private networking, and self-hosted applications that I use daily."
---

When people ask me about a project I'm proud of, I don't usually mention a traditional software project with a clear beginning and end. Instead, I talk about something that's been evolving for years and has become an integral part of my daily digital life: **my personal server infrastructure**.

This isn't just a hobby project. It's a living, breathing ecosystem of applications and services that I use every single day. From automatic deployments of my personal projects to a private VPN connecting all my devices, this infrastructure has become the backbone of my digital workflow.

## The Hardware Setup

My infrastructure spans multiple devices, each serving a specific purpose:

- **VPS (Virtual Private Server)**: The main server hosting most applications
- **Raspberry Pi**: Home server for local services and backup
- **Personal laptop**: Development machine and network client
- **Mobile phone**: Always-connected client with full network access

The beauty of this setup is that every device can seamlessly communicate with every other device, regardless of location or network restrictions.

## The Core Components

### 1. Private Network with Headscale

The foundation of everything is **Headscale**, an open-source alternative to Tailscale's control server. This creates a private mesh network connecting all my devices.

Here's how it works:
- Install Tailscale client on each device
- Connect all devices to my Headscale server
- Every device gets a private IP and can reach every other device
- My VPS acts as an exit node, giving me a free personal VPN

No more port forwarding, no more remembering IP addresses, no more VPN subscriptions. Just seamless connectivity everywhere.

### 2. Automated Deployment Pipeline

One of the features I'm most proud of is my automated deployment system. Here's the workflow:

1. **Write code** or create content (like blog posts)
2. **Push to GitHub** 
3. **GitHub Actions** automatically builds Docker images
4. **Webhook notification** sent to my server
5. **Server pulls** the new image and deploys using Docker Compose
6. **New version goes live** automatically

This means I can write code or create a blog post, push to GitHub, and watch the updates go live within minutes—no manual deployment steps required.

The projects that benefit from this automated deployment include:
- <img src="https://sahinakkaya.dev/favicon.svg" width="20" height="20"> [sahinakkaya.dev](https://sahinakkaya.dev) - My personal website
- <img src="https://blog.sahinakkaya.dev/assets/images/logo-96x96.png" width="20" height="20"> [blog.sahinakkaya.dev](https://blog.sahinakkaya.dev) - The blog you are currently reading
- <img src="https://progress.sahinakkaya.dev/favicon.png" width="20" height="20"> [progress.sahinakkaya.dev](https://progress.sahinakkaya.dev) - A personal habit tracker that I build for myself.
- <img src="https://chesslab.sahinakkaya.dev/logo.png" width="20" height="20"> [chesslab.sahinakkaya.dev](https://chesslab.sahinakkaya.dev) - A chess endgame and opening trainer that I build for myself.
- <img src="https://blackjack.sahinakkaya.dev/logo.svg" width="20" height="20"> [blackjack.sahinakkaya.dev](https://blackjack.sahinakkaya.dev) - A blackjack game implementation

Feel free to try all the applications I've shared above. I use them daily but not from these links, they are just demo versions.

### 3. Authentication Gateway

Security is crucial when self-hosting, so I run a centralized authentication system that protects all my applications. This gives me:
- Single sign-on across all self-hosted services
- Fine-grained access control
- Protection against unauthorized access
- Easy user management

### 4. Comprehensive Monitoring

I monitor everything with comprehensive tools that track uptime for all applications on both servers, send Telegram notifications when services go down, aggregate and display logs from all services, and monitor overall system health.

Getting a Telegram message at 3 AM because a service is down might not sound fun, but knowing about issues immediately means I can fix them before they impact my workflow.

## The Self-Hosted Application Suite

Over time, I've built up an impressive collection of self-hosted applications that replace traditional SaaS services:

### Media & Entertainment
Instead of paying for multiple streaming subscriptions, I run my own media server with tools for streaming my personal collection, tracking what I've watched, and managing my book library. This gives me complete control over my content without recurring fees.

- <img src="/assets/images/selfhost/jellyfin.png" width="20" height="20"> [**Jellyfin**](https://jellyfin.org) — streams my personal media collection
- <img src="/assets/images/selfhost/invidious.png" width="20" height="20"> [**Invidious**](https://invidious.io) — privacy-friendly YouTube front-end
- <img src="/assets/images/selfhost/movary.png" width="20" height="20"> [**Movary**](https://github.com/leepeuker/movary) — tracks movies I've watched
- <img src="/assets/images/selfhost/jelu.png" width="20" height="20"> [**Jelu**](https://github.com/bayang/jelu) — manages my book library and reading history

### Productivity & Personal Management
Rather than trusting third-party services with my personal data, I self-host my task management, note-taking, knowledge base, personal finance tracking, and password management. This ensures my sensitive information stays private and accessible only to me.

- <img src="/assets/images/selfhost/vikunja.png" width="20" height="20"> [**Vikunja**](https://vikunja.io) — task management and to-do lists
- <img src="/assets/images/selfhost/joplin.png" width="20" height="20"> [**Joplin**](https://joplinapp.org) — note-taking and personal knowledge base
- <img src="/assets/images/selfhost/actual-budget.png" width="20" height="20"> [**Actual Budget**](https://actualbudget.org) — personal finance tracking
- <img src="/assets/images/selfhost/vaultwarden.png" width="20" height="20"> [**Vaultwarden**](https://github.com/dani-garcia/vaultwarden) — self-hosted Bitwarden-compatible password manager

### Development & Technical Tools
My development workflow is entirely self-contained with private Git hosting, file management systems, document processing tools, and various utilities. This eliminates dependencies on external services and gives me full control over my code and projects.

- <img src="/assets/images/selfhost/gitea.png" width="20" height="20"> [**Gitea**](https://gitea.io) — private Git hosting
- <img src="/assets/images/selfhost/filebrowser.png" width="20" height="20"> [**File Browser**](https://filebrowser.org) — web-based file management
- <img src="/assets/images/selfhost/stirling-pdf.png" width="20" height="20"> [**Stirling PDF**](https://stirlingtools.com) — PDF editing and manipulation
- <img src="/assets/images/selfhost/convertx.png" width="20" height="20"> [**ConvertX**](https://github.com/C4illin/ConvertX) — image and file conversion
- <img src="/assets/images/selfhost/it-tools.png" width="20" height="20"> [**IT Tools**](https://github.com/CorentinTh/it-tools) — collection of handy developer utilities

### Infrastructure & Monitoring
The foundation that makes everything work includes authentication, networking, web traffic management, container orchestration, health monitoring, and automated backups. These tools ensure everything runs smoothly and securely while giving me complete visibility into how my systems are performing.

- <img src="/assets/images/selfhost/authentik.png" width="20" height="20"> [**Authentik**](https://goauthentik.io) — centralized authentication and SSO
- <img src="/assets/images/selfhost/caddy.png" width="20" height="20"> [**Caddy**](https://caddyserver.com) — reverse proxy and automatic HTTPS
- <img src="/assets/images/selfhost/uptime-kuma.png" width="20" height="20"> [**Uptime Kuma**](https://github.com/louislam/uptime-kuma) — uptime and health monitoring
- <img src="/assets/images/selfhost/kopia.png" width="20" height="20"> [**Kopia**](https://kopia.io) — encrypted, incremental backups

## Building Custom Solutions

When existing tools don't meet my specific needs, I build exactly what I want and publish it on GitHub. This approach gives me complete control over functionality without vendor lock-in while providing valuable learning opportunities.

## Why I'm Proud of This Project

This infrastructure project represents several things I value:

**Continuous Learning**: Every component teaches me something new about networking, DevOps, security, or system administration.

**Practical Value**: Unlike many side projects that gather dust, I use this infrastructure daily. Every improvement has immediate, tangible benefits.

**Complete Ownership**: I control my data, my services, and my digital environment. No surprise subscription price increases or feature removals.

**Technical Growth**: Managing this infrastructure has made me a better engineer, teaching me about scaling, reliability, monitoring, and automation.

**Cost Efficiency**: What would cost hundreds of dollars monthly in SaaS subscriptions runs on a single VPS for a fraction of the cost.

## Conclusion

Self-hosting has become one of my greatest passions, giving me complete control over my digital infrastructure while teaching me valuable skills along the way. This ongoing project represents the perfect blend of practical utility and continuous learning that makes it deeply rewarding.
