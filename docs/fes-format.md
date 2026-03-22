# .fes File Format Specification

`.fes` files are JSON data files that define festival dates by country for use in Pitara's photo auto-tagging system. When Pitara indexes a photo, it checks the capture date against all loaded festival files and tags the photo with any matching festival names.

---

## File naming

Each file represents one country. The file name should be the English country name with a `.fes` extension:

```
America.fes
India.fes
France.fes
Brazil.fes
```

---

## Top-level structure

```json
{
  "DataKeyPairDictionary": {
    ...
  }
}
```

There is one required top-level key: `DataKeyPairDictionary`. Its value is an object where each key is a festival name and each value is a festival entry.

---

## Festival entry structure

```json
"Festival Name": {
  "Name": "Festival Name",
  "Photos": {
    "1999": "Month Day",
    "2000": "Month Day",
    ...
    "2026": "Month Day"
  }
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `Name` | string | Yes | The display name of the festival. Must match the key exactly. |
| `Photos` | object | Yes | A dictionary of year strings to date strings. |

---

## Date format

Dates in the `Photos` dictionary follow this format:

```
"YYYY": "Month Day"
```

- **Key:** 4-digit year as a string — `"2023"`
- **Value:** Full month name followed by day number — `"November 3"`
- No leading zeros on the day — use `"July 4"` not `"July 04"`
- No year in the value — the year is already the key

**Valid examples:**
```json
"2023": "November 12",
"2024": "March 5",
"2025": "October 31"
```

**Invalid examples:**
```json
"2023": "11/12/2023",   ❌ wrong format
"2023": "12 November",  ❌ wrong order
"2023": "Nov 12",       ❌ abbreviated month
"2023": "November 12, 2023"  ❌ year in value
```

---

## Year coverage

Files should cover years **1999 through 2026** where data is available. Not every festival has well-documented dates before a certain year — it is acceptable to start from a later year if earlier dates are uncertain.

```json
"Holi": {
  "Name": "Holi",
  "Photos": {
    "2006": "March 14",
    "2007": "March 3",
    ...
    "2026": "March 3"
  }
}
```

---

## Fixed-date festivals

For festivals that fall on the same date every year, you may repeat the value across all years:

```json
"Christmas": {
  "Name": "Christmas",
  "Photos": {
    "1999": "December 25",
    "2000": "December 25",
    "2001": "December 25",
    ...
    "2026": "December 25"
  }
}
```

---

## Complete example

A minimal valid `.fes` file for France:

```json
{
  "DataKeyPairDictionary": {
    "Bastille Day": {
      "Name": "Bastille Day",
      "Photos": {
        "1999": "July 14",
        "2000": "July 14",
        "2001": "July 14",
        "2002": "July 14",
        "2003": "July 14",
        "2004": "July 14",
        "2005": "July 14",
        "2006": "July 14",
        "2007": "July 14",
        "2008": "July 14",
        "2009": "July 14",
        "2010": "July 14",
        "2011": "July 14",
        "2012": "July 14",
        "2013": "July 14",
        "2014": "July 14",
        "2015": "July 14",
        "2016": "July 14",
        "2017": "July 14",
        "2018": "July 14",
        "2019": "July 14",
        "2020": "July 14",
        "2021": "July 14",
        "2022": "July 14",
        "2023": "July 14",
        "2024": "July 14",
        "2025": "July 14",
        "2026": "July 14"
      }
    },
    "Easter Monday": {
      "Name": "Easter Monday",
      "Photos": {
        "1999": "April 5",
        "2000": "April 24",
        "2001": "April 16",
        "2002": "April 1",
        "2003": "April 21",
        "2004": "April 12",
        "2005": "March 28",
        "2006": "April 17",
        "2007": "April 9",
        "2008": "March 24",
        "2009": "April 13",
        "2010": "April 5",
        "2011": "April 25",
        "2012": "April 9",
        "2013": "April 1",
        "2014": "April 21",
        "2015": "April 6",
        "2016": "March 28",
        "2017": "April 17",
        "2018": "April 2",
        "2019": "April 22",
        "2020": "April 13",
        "2021": "April 5",
        "2022": "April 18",
        "2023": "April 10",
        "2024": "April 1",
        "2025": "April 21",
        "2026": "April 6"
      }
    }
  }
}
```

---

## Notes for contributors

- Do not include a `FilePath` field — that is an internal field used by the Pitara build system and is not part of the public format
- Validate your JSON before submitting — use any JSON linter or [jsonlint.com](https://jsonlint.com)
- For lunar calendar festivals, each year's date must be looked up individually — they shift every year
- See [CONTRIBUTING.md](../CONTRIBUTING.md) for the full contribution process
