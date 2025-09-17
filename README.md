# Monitoring Your Raspberry Pi with Prometheus and Grafana (Part 1: Local Setup)

This guide walks you through setting up **Prometheus**, **Node Exporter**, and **Grafana** on a Raspberry Pi to monitor system metrics (CPU, memory, temperature, etc.) on your local network. It’s perfect for DevOps beginners or hobbyists wanting to explore observability on a Pi. Part 2 will cover accessing this setup remotely via SSH.

Tested on a Raspberry Pi 4 running **Raspbian GNU/Linux 12 (bookworm)**.

---

## Why Monitor Your Raspberry Pi?
- **Prometheus**: A powerful time-series database that collects and stores metrics.
- **Node Exporter**: A Prometheus exporter that gathers system metrics (CPU, memory, disk, etc.).
- **Grafana**: A visualization tool to create dashboards for your metrics.
- Together, they let you track your Pi’s performance in real-time with cool graphs!

This guide assumes you have:
- A Raspberry Pi 4 with Raspbian installed.
- SSH enabled (`sudo raspi-config` > Interface Options > SSH > Enable).
- Basic terminal knowledge.
- Your Pi’s local IP (e.g., run `hostname -I` to find it).

---

## Step 1: Update Your Raspberry Pi
Ensure your Pi is up-to-date to avoid compatibility issues:
```bash
sudo apt update && sudo apt upgrade -y