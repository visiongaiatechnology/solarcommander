# 🌞 VGT Solar Commander — Mission Control HUD

[![License](https://img.shields.io/badge/License-AGPLv3-green?style=for-the-badge)](LICENSE)
[![PHP](https://img.shields.io/badge/PHP-8.0+-blue?style=for-the-badge&logo=php)](https://php.net)
[![WordPress](https://img.shields.io/badge/WordPress-6.0+-21759B?style=for-the-badge&logo=wordpress)](https://wordpress.org)
[![Rendering](https://img.shields.io/badge/Rendering-DIAMANT_V3-gold?style=for-the-badge)](#)
[![Status](https://img.shields.io/badge/Status-DIAMANT_VGT_SUPREME-purple?style=for-the-badge)](#)
[![VGT](https://img.shields.io/badge/VGT-VisionGaia_Technology-red?style=for-the-badge)](https://visiongaiatechnology.de)
[![Donate](https://img.shields.io/badge/Donate-PayPal-00457C?style=for-the-badge&logo=paypal)](https://www.paypal.com/paypalme/dergoldenelotus)

> *"Built for enthusiasts, researchers, and paranoid observers."*

**Solar Commander** is the cognitive interface for solar surveillance. A high-performance Mission Control HUD that transforms raw scientific telemetry into tactical intelligence — rendered in real-time directly inside your WordPress installation.

---

## 🛰️ What is Solar Commander?

Most space weather dashboards are either too complex, too slow, or send your users' data to third-party servers. Solar Commander is different: a fully self-hosted, modular HUD system that pulls live data from authoritative scientific sources and renders it through a Diamond-grade Glassmorphism interface — with zero external tracking.

---

## 📡 Telemetry Vectors — Full Sensor Coverage

| Vector | Sensor Source | Data |
|---|---|---|
| **X-Ray Flux / Flare History** | `GOES-16_XRAY_SENSOR` | Solar eruption classification from C to X-class with precise timestamp vectorization for CME prediction |
| **Geomagnetics** | `KYOTO_WDC_REALTIME` | Planetary K-Index strength and DST-Index (Disturbance Storm Time) — essential for understanding solar wind / magnetosphere interaction |
| **Solar Wind** | `NOAA_DSCOVR_SAT` | Real-time velocity, density and temperature of the solar wind plus interplanetary magnetic field (IMF) including Bt and Bz components |
| **SDO Imagery** | `NASA_SDO` | Live solar imagery across channels 171, 193, 304 and HMI Magnetogram |

---

## 🔭 Aurora Scope Technology

Solar Commander includes a **predictive algorithm for aurora forecasting**. By correlating solar wind velocity ($V$) and magnetic field orientation ($Bz$), the system calculates the probability of geomagnetic storms from G1 to G5.

```
Aurora Scope Status:
├── Confidence:  94%
├── Lat_Min:     52° N
└── State:       ACTIVE
```

---

## ⚙️ Modular Architecture

### 01 — PHP Template Engine
Every widget (Flare History, KP-Index, Solar Wind, etc.) is an autonomous PHP template. Easy to extend, extremely performant during rendering.

```php
/** SOLAR_HUD: SUN_IMAGER_MODULE */
$channels = ['171', '193', '304', 'HMI'];
foreach ($channels as $ch): ?>
    <div class="hud-imager-slot" data-channel="<?php echo $ch; ?>">
        <span class="channel-id">CH_<?php echo $ch; ?></span>
        <div class="image-viewport">
            <img src="<?php echo $placeholder; ?>" data-live-src="..." />
        </div>
        <div class="slot-footer">
            <div class="telemetry-bar"></div>
        </div>
    </div>
<?php endforeach;
```

### 02 — Asynchronous JS Engine
`vg-solar-engine.js` controls the asynchronous data flow. No page reloads required — the HUD breathes in sync with solar telemetry.

### 03 — Diamond HUD CSS
A dedicated skin combining Glassmorphism and asymmetric layouts. Optimized for dark-mode environments. Built to the DIAMANT V3 rendering standard.

---

## 🏗️ System Architecture

```
VGT Sovereign Code Structure // Deterministic Output

├── templates/
│   └── visuals/
│       ├── sun-imager.php        ← SDO Multi-Channel Renderer
│       ├── flare-history.php     ← GOES-16 Eruption Tracker
│       ├── kp-index.php          ← Geomagnetic Storm Monitor
│       └── solar-wind.php        ← DSCOVR Real-Time Feed
├── assets/
│   ├── vg-solar-engine.js        ← Async Telemetry Engine
│   └── diamond-hud.css           ← Glassmorphism HUD Skin
└── solar-commander.php           ← Core Bootstrap
```

---

## 🚀 Installation

### Requirements
- WordPress 6.0+
- PHP 8.0+
- cURL enabled

### Setup

1. Download and extract to `/wp-content/plugins/vgt-solar-commander/`
2. Activate via **Plugins → Installed Plugins**
3. Place the HUD on any page or post using the shortcode

### Shortcode Usage

```php
// Full Mission Control HUD:
[solar_commander]

// Individual modules:
[solar_commander module="flares"]
[solar_commander module="kp_index"]
[solar_commander module="solar_wind"]
[solar_commander module="aurora_scope"]
[solar_commander module="sdo_imagery"]
```

---

## 📊 Live HUD Preview

```
MISSION CONTROL HUD v3.2
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
X-RAY FLUX      ████████░░  C2.4
KP-INDEX        ██████████  G2 (STORM)
AURORA SCOPE    ACTIVE — 52°N / 94% confidence
SOLAR WIND      623 km/s | Bz: -12nT (SOUTH)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
UPLINK: NOAA_DSCOVR_SAT // GOES-16 // KYOTO_WDC
```

---

## 🔒 Privacy & Sovereignty

- All data fetching runs **server-side** — your visitors' IPs never reach NOAA, NASA or any external API
- No analytics, no tracking, no third-party dependencies loaded client-side
- Fully **GDPR / Schrems II compliant**

---

## 🤝 Contributing

Pull requests are welcome. For major changes please open an issue first.

Licensed under **GNU AGPLv3** — open source, sovereign, free forever.

---

## ☕ Support the Project

Solar Commander is free. If it powers your space weather station:

[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-00457C?style=for-the-badge&logo=paypal)](https://www.paypal.com/paypalme/dergoldenelotus)

---

## 🏢 Built by VisionGaia Technology

[![VGT](https://img.shields.io/badge/VGT-VisionGaia_Technology-red?style=for-the-badge)](https://visiongaiatechnology.de)

VisionGaia Technology builds enterprise-grade security and AI tooling — engineered to the DIAMANT VGT SUPREME standard.

> *"In a world of centralized tracking madness, Solar Commander is an autonomous node of digital freedom."*

---

*Version 3.2 — Mission Control HUD // Rendering Engine: DIAMANT_V3*
