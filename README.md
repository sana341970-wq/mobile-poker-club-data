# Mobile Poker Club Data

Open, machine-readable dataset tracking listed mobile poker clubs across PPPoker, PokerBros, ClubGG and X-Poker. Maintained by [Poker Catalog](https://pppoker-catalog.com) and James Holden, Editor-in-Chief and Lead Analyst.

The July 2026 edition contains 11 club records from the current public catalog. It includes application, union, advertised maximum rakeback, reported peak-traffic range, games, stakes, countries, NFND availability, jackpot availability and the date of the underlying listing.

## Files

- [`clubs.json`](clubs.json) — canonical structured club dataset
- [`clubs.csv`](clubs.csv) — flattened version for spreadsheets and analysis
- [`clubs.schema.json`](clubs.schema.json) — JSON Schema for `clubs.json`
- [`apps-comparison.csv`](apps-comparison.csv) — application-level comparison
- [`rake-glossary.md`](rake-glossary.md) — terminology reference
- [`snapshots/2026-07.json`](snapshots/2026-07.json) — July 2026 reported traffic snapshot
- [`METHODOLOGY.md`](METHODOLOGY.md) — collection and field rules
- [`DATA_QUALITY.md`](DATA_QUALITY.md) — known source conflicts and quality notes
- [`SECURITY.md`](SECURITY.md) — safe reporting and disclosure policy
- [`CITATION.cff`](CITATION.cff) — citation metadata for GitHub and Zenodo

## Quick start

```python
import json

with open("clubs.json", encoding="utf-8") as source:
    dataset = json.load(source)

print(dataset["snapshot_date"], len(dataset["clubs"]))
```

## Data notes

- `max_rakeback_percent` is the maximum advertised rate, not a guaranteed personal offer. Actual terms may depend on volume and must be confirmed before play.
- `peak_traffic` is a reported range shown by the source listing. It is not an independent real-time player count.
- `club_id` is `null` when the public listing says to ask the listed representative. This dataset does not infer or republish unverified access codes.
- `nfnd` is `true` only when the current catalog card explicitly displays **NFND**. Otherwise it is `false`; club rules can change.
- The dataset describes publicly listed information and does not endorse a club, agent or financial arrangement.
- App-level summaries and individual club listings can disagree. Both source values are preserved and known conflicts are recorded in [`DATA_QUALITY.md`](DATA_QUALITY.md).

## Sources and updates

The canonical source is the [Poker Catalog club directory](https://pppoker-catalog.com/clubs/), with one source URL recorded for every club and app. Data is reviewed monthly; dated JSON files preserve what the source reported at each observation.

Corrections are welcome through GitHub issues or pull requests. Please include a public source and the date it was checked.

Every pull request and update to `main` runs a read-only consistency check covering JSON syntax, duplicate slugs, source URLs and alignment between JSON, CSV and the monthly snapshot.

## Responsible use

For informational and research use only. Poker laws vary by location. Users must be 18+ (or meet their local legal age), check local regulations and assess independent-agent risk before transferring funds. If gambling is causing harm, visit [GambleAware](https://www.gambleaware.org/).

## License and citation

The dataset and documentation are licensed under [Creative Commons Attribution 4.0 International](LICENSE). Attribution: **Poker Catalog / James Holden** with a link to <https://pppoker-catalog.com>.

Preferred citation:

> Holden, James. (2026). *Mobile Poker Club Data* (2026.07) [Data set]. Poker Catalog. https://github.com/sana341970-wq/mobile-poker-club-data
