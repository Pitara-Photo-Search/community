# Pitara Query Syntax Reference

Pitara understands natural language. You don't need special operators — just describe what you're looking for and Pitara figures out the rest. This document covers every query type the engine supports.

---

## Basic text search

Type any word and Pitara searches tags, locations, and keywords associated with your photos.

```
beach
mountains
family
graduation
```

Combine words freely — Pitara treats them as AND by default:

```
beach family summer
mountains snow hiking
```

---

## Time of Day

Pitara auto-tags every photo based on the hour it was taken.

| Tag | Time range |
|-----|-----------|
| `Morning` | 6:00 AM – 11:59 AM |
| `Noon` | 12:00 PM exactly |
| `Afternoon` | 1:00 PM – 4:59 PM |
| `Evening` | 5:00 PM – 7:59 PM |
| `Night` | 8:00 PM onwards |

**Example queries:**
```
beach morning
family dinner evening
kids afternoon birthday
```

---

## Day of Week

```
Monday  Tuesday  Wednesday  Thursday  Friday  Saturday  Sunday
```

Pitara also understands:

| Query word | Meaning |
|-----------|---------|
| `Weekday` | Monday through Friday |
| `Weekend` | Saturday and Sunday |

**Example queries:**
```
kids weekend morning
office lunch weekday
birthday Saturday
```

---

## Week of Month

Pitara tags each photo with the week of the month it falls in.

| Tag | Meaning |
|-----|---------|
| `FirstWeek` | Days 1–7 |
| `SecondWeek` | Days 8–14 |
| `ThirdWeek` | Days 15–21 |
| `FourthWeek` | Days 22–28 |
| `FifthWeek` | Days 29–31 (where they exist) |
| `LastWeek` | The final week of the month |

**Example queries:**
```
first week december family
last week january snow
third week august vacation beach
```

---

## Months

Use the full month name:

```
January  February  March  April  May  June
July  August  September  October  November  December
```

**Example queries:**
```
march holi colors
august mountains trek
december christmas family
```

---

## Seasons

| Query word | Months covered |
|-----------|---------------|
| `Spring` | March, April, May |
| `Summer` | June, July, August |
| `Autumn` / `Fall` | September, October, November |
| `Winter` | December, January, February |

**Example queries:**
```
summer beach kids
autumn leaves hiking
winter snow family
```

---

## Year

Search by a specific year or a range of years.

**Single year:**
```
birthday 2022
Paris 2019
```

**Year range** (use "to" between years):
```
travel 2018 to 2022
kids 2015 to 2020
beach vacation 2019 to 2023
```

---

## Relative Time

Pitara understands relative date expressions.

```
last summer
last winter
3 years ago
5 years ago
```

**Example queries:**
```
beach last summer
family last christmas
hiking 2 years ago
```

---

## Location

Pitara extracts GPS coordinates from your photos' EXIF data and reverse-geocodes them to city and country names. Search by any part of the location.

```
Tokyo
Paris
New York
India
Kyoto evening
beach Thailand 2020
```

---

## Camera Make and Model

Pitara reads the camera make and model from EXIF data.

```
iPhone
Canon
Nikon
Sony
Fujifilm
iPhone 13
Canon EOS
Nikon D750
```

**Example queries:**
```
iPhone morning kids
Canon beach sunset
Fujifilm Tokyo street
Sony evening portrait
```

---

## Altitude / Elevation

Pitara reads altitude from EXIF data and supports elevation range queries.

```
above 5000 feet
above 8000 feet
above 3000 feet
high altitude trek
```

**Example queries:**
```
mountains above 8000 feet
trek above 5000 feet summer
Himalayas above 10000 feet
```

---

## Festivals

Pitara tags photos that fall on festival dates based on your selected country profile. Search by festival name directly.

**American festivals:**
```
Thanksgiving  Labor Day  Memorial Day  Easter  Mardi Gras  Mother's Day  Father's Day
```

**Indian festivals:**
```
Diwali  Holi  Rakhi  Janmashtami  Dussehra  Maha Shivaratri
```

**Chinese festivals:**
```
Chinese New Year  Lantern Festival  Mid-Autumn Festival  Dragon Boat Festival  Qingming
```

**Japanese festivals:**
```
Tanabata  Obon  Hinamatsuri  Setsubun  Shichi-Go-San
```

**UK festivals:**
```
Boxing Day  Guy Fawkes  Easter Monday  Spring Bank Holiday
```

**Canadian festivals:**
```
Canada Day  Victoria Day  Remembrance Day  Family Day
```

**Spanish festivals:**
```
La Tomatina  San Fermin  Feria de Abril  Three Kings Day
```

**Example queries:**
```
Diwali family 2022
Thanksgiving 2019 dinner
Chinese New Year kids
Holi colors 2023
```

---

## Combining Query Types

All query types can be combined freely. Pitara treats each token as an AND condition.

```
Canon evening Tokyo 2022
iPhone morning weekday kids 2021 to 2023
Diwali family evening October
beach summer Canon above 3000 feet
first week december christmas family evening
```

---

## Advanced: Direct Lucene Syntax

For power users, Pitara's search bar accepts raw Lucene query syntax. The underlying fields are:

| Field | Description | Example |
|-------|-------------|---------|
| `Tags` | Auto-tags and custom tags | `Tags:beach` |
| `Location` | Reverse-geocoded place name | `Location:Tokyo` |
| `DateTimeKeywords` | Date/time tokens | `DateTimeKeywords:Morning` |
| `KeyWords` | General keywords from metadata | `KeyWords:family` |
| `CameraModel` | Camera model from EXIF | `CameraModel:iPhone` |
| `CameraMake` | Camera manufacturer | `CameraMake:Canon` |
| `EPOCHTIME` | Unix timestamp (for ranges) | `EPOCHTIME:[1640995200 TO 1672531200]` |
| `Altitude` | Altitude in feet | (used internally for range queries) |

**Example raw query:**
```
Tags:beach DateTimeKeywords:Summer EPOCHTIME:[1546300800 TO 1609459200]
```

---

## Tips

- Spelling doesn't need to be perfect — Pitara handles common variants
- Singular and plural are treated the same ("photo" = "photos")
- Case doesn't matter — "BEACH" and "beach" return the same results
- If a query returns too many results, add more words to narrow it down
- If a query returns nothing, try removing words to broaden it
