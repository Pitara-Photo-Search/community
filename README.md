# Pitara — Community Data & Extensions

This is the official community repository for **Pitara**, a free privacy-first photo search application for Windows.

> Find any photo in your local library in under half a second — using plain English. No cloud. No account. No telemetry.
>
> **[Download Pitara free at GetPitara.com](https://www.getpitara.com)**

---

## What's in this repo

| Folder | Contents |
|--------|----------|
| [`festivals/`](festivals/) | Festival date data files for 7 countries (1999–2026) |
| [`plugins/`](plugins/) | Plugin system — coming soon. Placeholder and spec in progress. |
| [`docs/query-syntax.md`](docs/query-syntax.md) | Full reference for Pitara's natural language query syntax |
| [`docs/fes-format.md`](docs/fes-format.md) | Specification for the `.fes` festival data file format |

---

## Festival Data

Pitara tags photos automatically based on the festivals that fall on or near their capture date. When you search *"Diwali photos"* or *"Chinese New Year 2019"*, Pitara matches photos taken on those exact dates.

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

All files cover dates from **1999 to 2026**.

**Want to add your country?** See [CONTRIBUTING.md](CONTRIBUTING.md).
Countries we'd love next: Brazil, Mexico, Germany, France, Australia, South Korea, Nigeria, Egypt.

---

## Plugin System *(coming soon)*

Pitara is being designed to support community-built plugins. The first planned plugin type is **custom tag providers** — letting developers add new tabs and tagging logic to the app without modifying Pitara's core.

See [`plugins/README.md`](plugins/README.md) for the roadmap and how to get notified when the plugin API is ready.

---

## Query Syntax

Pitara understands natural language. You don't need special operators — just describe what you're looking for.

```
beach sunset 2022
kids birthday morning
Paris last summer
iPhone weekday morning 2021 to 2023
mountain above 8000 feet
Canon camera first week December
```

Full reference → [`docs/query-syntax.md`](docs/query-syntax.md)

---

## Contributing

- **Festival data** — Add a new country or fix dates. See [CONTRIBUTING.md](CONTRIBUTING.md).
- **Plugin ideas** — Open an issue tagged `plugin-request` to suggest what you'd want to build.
- **Query bugs** — If a search query doesn't work as expected, open an issue with the query and what you expected.

---

## License

Festival data, plugin specs, and documentation in this repository are released under the [MIT License](LICENSE).

The Pitara application itself is proprietary. Only the community data and docs in this repo are open source.

---

## About Pitara

Pitara is a Windows desktop app that builds a local Lucene search index from your photo folders and lets you search them with plain English queries. Everything runs on your PC — no photos are ever uploaded anywhere.

- Sub-0.5 second search across 100,000+ photos
- Understands time, location, camera, season, elevation, and festivals
- Free for all early users
- Windows 10 / 11, 64-bit
- Built by [Naren](https://www.getpitara.com/about)

**[GetPitara.com](https://www.getpitara.com)**
