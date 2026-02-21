<p align="center">
  <img src="assets/match-report-epl.png" width="450" alt="FCAI Match Report - Man Utd vs Fulham">
</p>

<h1 align="center">FCAI - Football Chart & Analysis Insights</h1>

<p align="center">
  <em>Automated football match visualizations powered by xG data</em>
</p>

---

## About

FCAI generates professional match report infographics from a single CLI command. It pulls data from multiple APIs, processes it through a caching pipeline, and renders publication-ready visuals.

- **Format**: 1080x1920px (Instagram Story, 9:16 aspect ratio)
- **Output**: Static reports (PNG) and animated reports (MP4 with audio)
- **Data**: xG values, shot positions, injury time, team logos — all fetched and merged automatically

---

## Gallery

### Match Reports

<table>
  <tr>
    <td align="center"><strong>EPL (Dark Theme)</strong></td>
    <td align="center"><strong>Ekstraklasa (Light Theme)</strong></td>
  </tr>
  <tr>
    <td><img src="assets/match-report-epl.png" width="400" alt="EPL Match Report"></td>
    <td><img src="assets/match-report-ekstraklasa.png" width="400" alt="Ekstraklasa Match Report"></td>
  </tr>
</table>

### Animation

<table>
  <tr>
    <td align="center" width="400">
      <a href="assets/match-animation.mp4">
        <img src="assets/match-report-epl.png" width="400" alt="Click to watch animation">
        <br>
        <strong>Watch animation (MP4)</strong>
      </a>
    </td>
    <td>
      <strong>75-second animated match report</strong>
      <br><br>
      <ul>
        <li>Progressive shot-by-shot build at 30fps</li>
        <li>1.2s pause on each goal with audio cue</li>
        <li>Background music with automatic ducking</li>
        <li>Hook intro + crossfade + outro scenes</li>
        <li>H.264 codec, Instagram-ready</li>
      </ul>
    </td>
  </tr>
</table>

### League Analytics

<table>
  <tr>
    <td align="center"><strong>xGA vs xG Diamond</strong></td>
    <td align="center"><strong>xG Differential</strong></td>
  </tr>
  <tr>
    <td><img src="assets/diamond-chart.png" width="400" alt="Diamond Chart - xGA vs xG"></td>
    <td><img src="assets/xg-differential.png" width="400" alt="xG Differential Bar Chart"></td>
  </tr>
</table>

### Pre-match

<p align="center">
  <img src="assets/teams-clash.png" width="500" alt="Teams Clash - Form Comparison">
</p>

---

## Features

- **Multi-source data pipeline** — 3 APIs with caching, rate limiting, and automatic retry
- **Fuzzy name matching** — resolves team name discrepancies between different data providers
- **Delta E CIE2000 color contrast** — automatically picks contrasting team colors for readability
- **Injury time handling** — splits added time per half for accurate timeline positioning
- **Animated reports** — 30fps video with goal pauses and audio with ducking
- **Dark & light themes** — optimized color palettes per theme
- **600 DPI output** — publication-quality, Instagram-ready format

---

## Architecture

```mermaid
graph LR
    A[CLI] --> B[Data Pipeline]
    B --> C[Source 1]
    B --> D[Source 2]
    B --> E[Source 3]
    C & D & E --> F[Cache Layer]
    F --> G[Match Model — JSON]
    G --> H[Static Renderer → PNG]
    G --> I[Animation Renderer → MP4]
    I --> J[SocialMedia 1]
    I --> K[SocialMedia 2]
    I --> L[SocialMedia 3]
```

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![matplotlib](https://img.shields.io/badge/matplotlib-Visualization-11557C)
![mplsoccer](https://img.shields.io/badge/mplsoccer-Pitch%20Plots-2E8B57)
![pandas](https://img.shields.io/badge/pandas-Data-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Compute-013243?logo=numpy&logoColor=white)
![moviepy](https://img.shields.io/badge/moviepy-Video-FF6F00)
![Pillow](https://img.shields.io/badge/Pillow-Images-FFD43B)
![Click](https://img.shields.io/badge/Click-CLI-000000)

| Category | Libraries |
|----------|-----------|
| **Visualization** | matplotlib, mplsoccer, Pillow |
| **Data** | pandas, numpy |
| **Animation** | moviepy (H.264) |
| **CLI** | click, rich |
| **Networking** | tenacity (retry), requests |
| **Color Science** | colormath (Delta E CIE2000) |

---

## Roadmap

- [x] Match report (PNG)
- [x] Animated report (MP4 with audio)
- [x] Dark & light themes
- [x] Multi-league support
- [ ] Round summary (automated xG diamond chart)
- [ ] European competitions (UCL, UEL, UECL)
- [ ] More leagues (La Liga, Bundesliga, Serie A, Ligue 1)
- [ ] Social media publication

---

<p align="center">
  <strong>@k_o_n_rad</strong>
  <br>
  <sub>Source code is private. This repository showcases outputs only.</sub>
</p>
