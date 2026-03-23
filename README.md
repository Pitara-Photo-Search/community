# Pitara — Community Data & Extensions

[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-blue)](https://www.getpitara.com/download)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Download](https://img.shields.io/badge/download-free-brightgreen)](https://www.getpitara.com/download)

A free, on-device alternative to Google Photos search — no upload, no account, no cloud.

> *Pitara (पिटारा) — Hindi for "box of surprises." That's exactly what your photo library is.*

**[Download Pitara free at GetPitara.com](https://www.getpitara.com)**

---

![Pitara screenshot](assets/screenshot.png)

---

## What is Pitara?

Pitara is a Windows desktop app that lets you search your entire local photo library using plain English — in under half a second, across 100,000+ photos, with nothing ever leaving your machine.

Type what you remember:

```
paris morning 2023
iPhone summer kids birthday
FirstWeek december evening family
mountain above 8000 feet
from 2018 to 2022 sammamish weekend
```

Pitara has eight built-in tabs — **Search, Places, Times, Cameras, Tags, Folders, Hikes, and Festivals** — and a plugin system coming soon that will let the community add new ones.

- Sub-0.5 second search across 100,000+ photos
- Understands time of day, day of week, season, year ranges, location, camera, altitude, festivals, and custom tags
- 100% on-device — no account, no upload, zero telemetry
- Free · Windows 10 / 11 · 64-bit

---

## What's in this repo

| Folder | Contents |
|--------|----------|
| [`festivals/`](festivals/) | Festival date data files for 7 countries (1999–2026) |
| [`plugins/`](plugins/) | Plugin system — coming soon. Spec and roadmap in progress. |
| [`docs/query-syntax.md`](docs/query-syntax.md) | Full reference for Pitara's natural language query syntax |
| [`docs/fes-format.md`](docs/fes-format.md) | Specification for the `.fes` festival data file format |

---

## Festival Data

Pitara tags photos automatically based on festivals that fall on or near their capture date. Search *"Diwali photos"* or *"Chinese New Year 2019"* and Pitara matches photos taken on those exact dates.

### Countries included

| File | Country | Festivals included |
|------|---------|-------------------|
| [`America.fes`](festivals/America.fes) | United States | Thanksgiving, Labor Day, Memorial Day, Mother's Day, Father's Day, Easter, Mardi Gras |
| [`India.fes`](festivals/India.fes) | India | Diwali, Holi, Rakhi, Janmashtami, Dussehra, Anant Chaturdashi, Maha Shivaratri |
| [`China.fes`](festivals/China.fes) | China | Chinese New Year, Lantern Festival, Qingming, Dragon Boat Festival, Mid-Autumn Festival, Double Ninth, Winter Solstice |
| [`Canada.fes`](festivals/Canada.fes) | Canada | Victoria Day, Canada Day, Labour Day, Thanksgiving, Remembrance Day, Family Day, Easter Monday |
| [`Japan.fes`](festivals/Japan.fes) | Japan | New Year, Setsubun, Hinamatsuri, Showa Day, Tanabata, Obon, Shichi-Go-San |
| [`Spain.fes`](festivals/Spain.fes) | Spain | Three Kings Day, Easter Sunday, San José, Feria de Abril, San Fermín, La Tomatina, National Day |
| [`UK.fes`](festivals/UK.fes) | United Kingdom | Easter Sunday, Easter Monday, Early May Bank Holiday, Spring Bank Holiday, Summer Bank Holiday, Guy Fawkes Night, Boxing Day |

All files cover **1999 to 2026**.

**Want to add your country?** See [CONTRIBUTING.md](CONTRIBUTING.md).
Countries we'd love next: Brazil, Mexico, Germany, France, Australia, South Korea, Nigeria, Egypt.

---

## Plugin System *(coming soon)*

Pitara is being designed to support community-built plugins. The first planned type is **custom tag providers** — letting developers add new tabs and tagging logic without modifying Pitara's core.

See [`plugins/README.md`](plugins/README.md) for the roadmap and how to get notified when the API is ready.

---

## Query Syntax

Full reference with real-life examples → [`docs/query-syntax.md`](docs/query-syntax.md)

More resources on the website:
- [Sample Searches](https://www.getpitara.com/sample-searches) — 50+ working query examples
- [User Guide](https://www.getpitara.com/user-guide) — getting started, tabs, keyboard shortcuts
- [FAQ](https://www.getpitara.com/faq) — common questions

---

## Contributing

- **Festival data** — Add a new country or fix dates. See [CONTRIBUTING.md](CONTRIBUTING.md).
- **Plugin ideas** — Open an issue tagged `plugin-request` to suggest what you'd want to build.
- **Query bugs** — If a search doesn't work as expected, open an issue with the query and what you expected.

---

## License

Festival data, plugin specs, and documentation are released under the [MIT License](LICENSE).

The Pitara application itself is proprietary. Only the community data and docs in this repo are open source.

---

## About

Built by [Naren](https://www.getpitara.com/about) — a developer who believes privacy-first software should be fast, free, and actually work.

**[GetPitara.com](https://www.getpitara.com)**

---

*If Pitara saves you time finding memories, a ⭐ helps others find it.*
