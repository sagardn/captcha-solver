# 🧠 CAPTCHA Solver

<p align="center">
  <strong>High-performance CAPTCHA solving toolkit for automation & web scraping</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-active-success?style=flat-square">
  <img src="https://img.shields.io/badge/python-3.8+-blue?style=flat-square">
  <img src="https://img.shields.io/badge/license-MIT-green?style=flat-square">
  <img src="https://img.shields.io/badge/architecture-modular-orange?style=flat-square">
</p>

---

## 🚀 Features

- ✅ **Multi-provider support** — plug in any solving backend
- ⚡ **Async solving engine** — high throughput, non-blocking
- 🔁 **Callback system** — event-driven result handling
- 🔌 **REST API** — simple HTTP interface for any language
- 🧩 **Modular architecture** — extend with custom solvers
- 🌐 **Proxy support** — full proxy rotation (IP:Port:User:Pass)
- 🔐 **Session-based solving** — maintain state across requests

---

## 🧩 Supported CAPTCHA Types

| CAPTCHA Type            | Status |
|------------------------|--------|
| reCAPTCHA v2           | ✅ |
| reCAPTCHA v3           | ✅ |
| Cloudflare Turnstile   | ✅ |
| AWS WAF                | ✅ |
| GeeTest                | ✅ |
| MTCaptcha              | ✅ |
| Prosopo                | ✅ |
| TikTok                 | ✅ |
| Binance                | ✅ |
| Tencent                | ✅ |
| Slide CAPTCHA          | ✅ |

---

## ⚡ Quick Start

```python
from captcha_solver import Solver

solver = Solver(api_key="your_api_key")

# Solve reCAPTCHA v2
token = solver.solve(
    captcha_type="recaptcha_v2",
    site_key="6Le-wvkSAAAAAPBMRTvw0Q4Muexq9bi0DJwx_mJ-",
    page_url="https://example.com",
)
print(f"Token: {token}")
```

---

## 🔑 Token Types

| Token | Description |
|-------|-------------|
| 🔐 reCAPTCHA Token | Google reCAPTCHA v2/v3 response |
| 🔐 Turnstile Token | Cloudflare challenge response |
| 🔐 GeeTest Token | GeeTest challenge validation |

---

## 🏗️ Architecture

```
Client Request
    │
    ▼
┌──────────────┐
│   REST API   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Task Router  │  ← Routes to correct solver
└──────┬───────┘
       │
       ▼
┌──────────────┐
│   Solvers    │  ← Modular solver plugins
│  ┌────────┐  │
│  │ reCAPT │  │
│  │ Turnst │  │
│  │ GeeTest│  │
│  └────────┘  │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│  Callback    │  ← Return token to client
└──────────────┘
```

---

## 🌐 Proxy Configuration

```python
solver = Solver(
    api_key="your_api_key",
    proxy="ip:port:username:password",
    proxy_type="http"  # http, socks5
)
```

---

## 📄 License

MIT — use it, fork it, build on it.

---

## 📞 Contact

[![Telegram](https://img.shields.io/badge/Telegram-Contact-blue?style=for-the-badge&logo=telegram)](https://t.me/QAM_07)
