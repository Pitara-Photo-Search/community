# Contributing to Pitara Festival Data

Thank you for helping make Pitara smarter for more cultures and countries. This guide explains how to contribute new festival data files or improve existing ones.

---

## What we need

- **New country files** — festivals for countries not yet covered
- **Missing years** — extending existing files beyond 2026
- **Corrections** — fixing wrong dates in existing files
- **New festivals** — adding culturally significant events to existing country files

---

## File format

Festival data files use the `.fes` extension and contain JSON. See [`docs/fes-format.md`](docs/fes-format.md) for the complete specification.

**Quick example — a minimal valid file:**

```json
{
  "DataKeyPairDictionary": {
    "Bastille Day": {
      "Name": "Bastille Day",
      "Photos": {
        "1999": "July 14",
        "2000": "July 14",
        "2026": "July 14"
      }
    }
  }
}
```

**Rules:**
- File name must match the country (e.g., `France.fes`)
- Date format is always `"Month Day"` — e.g., `"July 14"`, `"November 3"` (no leading zeros, no year in value)
- Cover years 1999 through 2026 where possible
- Use the official English name of the festival as the key and in the `Name` field
- Do not include the `FilePath` field — that is an internal field not used in submissions

---

## How to add a new country

1. **Fork** this repository
2. Create a new file in the `festivals/` folder named `[Country].fes`
3. Follow the format in [`docs/fes-format.md`](docs/fes-format.md)
4. Include at least 3 festivals with dates for 1999–2026
5. Add your country to the table in `README.md`
6. Open a **Pull Request** with:
   - The new `.fes` file
   - The README update
   - A brief note on your data sources

---

## Data accuracy

Festival dates matter — a wrong date means photos get tagged incorrectly. Please:

- Use authoritative sources: official government calendars, Wikipedia with citations, or established cultural organizations
- For lunar calendar festivals (Diwali, Chinese New Year, etc.), verify each year's date individually — they shift every year
- For fixed-date festivals (Christmas, Canada Day, etc.), a single entry repeated across all years is fine
- If you're uncertain about a date, leave that year out rather than guessing

---

## Correcting existing dates

If you find a wrong date in an existing file:

1. Open an **Issue** describing the error (country, festival, year, current date, correct date, and source)
2. Or submit a **Pull Request** with the fix directly

---

## What not to include

- Commercial events (Black Friday, Prime Day)
- Sports events
- Events specific to a single city rather than a country
- Public figures' birthdays

Stick to widely observed cultural, religious, or national holidays.

---

## Questions?

Open an issue or reach out via [GetPitara.com](https://www.getpitara.com).
