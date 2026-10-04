# Stellenabbau-Tracker · Open Data (Germany)

[![Data License: CC BY 4.0](https://img.shields.io/badge/Data-CC_BY_4.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Update: daily](https://img.shields.io/badge/Update-daily-green.svg)](https://stellenabbau.hunterfang.com/rss.xml)

Open dataset of publicly reported mass layoffs, plant closures, and restructuring programs in **Germany** — tracked since 2024, updated daily.

**Website & live tracker:** <https://stellenabbau.hunterfang.com>

## Why this dataset exists

Unlike the US (WARN Act database), Germany has **no public database for Massenentlassungsanzeigen** (§ 17 KSchG). Every number floating around in public debate comes from scattered news reports. This project aggregates them — with a source link for every single record.

## Files

| File | Content |
|---|---|
| `data-records.json` | One JSON object per documented layoff event: company, date, number of employees, scope, status, locations, type, source link |
| `data-companies.json` | Company directory: slug, name, industry, HQ, aliases, documented severance parameters where available |

## Data model (records)

```json
{
  "id": "vw-2024-12",
  "company": "volkswagen",
  "date": "2024-12-20",
  "employees": 35000,
  "scope": "Deutschland",
  "locations": ["Wolfsburg", "Zwickau"],
  "states": ["niedersachsen"],
  "status": "bestaetigt | gefaehrdet | geruecht",
  "type": "massenentlassung | werkschliessung | umstrukturierung | insolvenz",
  "title": "...",
  "note": "...",
  "source": { "publisher": "...", "url": "https://..." }
}
```

**Status definitions:**
- `bestaetigt` — confirmed by the company, works council, authorities, or consistent primary reporting
- `gefaehrdet` — credible media reports exist, no official confirmation yet
- `geruecht` — vague or contradictory reporting

## Known limitations (be honest when citing)

- Only **publicly reported** cases are included — the dark figure is higher
- Companies often communicate "up to" numbers; treat figures as upper bounds
- Coverage started 2024; historical cases are being backfilled
- No individual-level data (company level only, GDPR-safe by design)

## License & citation

**CC BY 4.0** — free for journalism, research, and commercial use with attribution:

> Stellenabbau-Tracker (stellenabbau.hunterfang.com), CC BY 4.0

For journalists: methodology and source list at <https://stellenabbau.hunterfang.com/datenquellen/>. Corrections welcome: `fang_hongtao@163.com`.

## Updates

This dataset syncs automatically from the [live tracker](https://stellenabbau.hunterfang.com) every day. Machine-readable updates also via [RSS](https://stellenabbau.hunterfang.com/rss.xml) and [llms-full.txt](https://stellenabbau.hunterfang.com/llms-full.txt).
