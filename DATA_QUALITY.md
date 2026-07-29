# Data Quality Notes

## What “accurate” means here

The values in this repository are accurate transcriptions of public Poker Catalog pages observed on 2026-07-29. They are not independent audits of live traffic, payment performance, club access or commercial terms.

Each club record keeps its own source URL and the source page's update date. Public Club IDs are not inferred: `club_id` remains `null` when the listing directs readers to a representative.

## Known source conflicts

Two app-level maximums disagree with individual club listings:

| Field | App page | Individual club page | Dataset treatment |
|---|---:|---:|---|
| X-Poker maximum rakeback | 50% | Game Of Molly: 60% | Both values preserved; club record uses 60% |
| PPPoker maximum rakeback | 60% | Molly's: 65% | Both values preserved; club record uses 65% |

These conflicts are also machine-readable in `clubs.json` under `known_source_conflicts`. The repository does not silently “correct” either source.

## Reliability by field

- **High transcription confidence:** name, app, union, games, stakes, countries, source URL and source update date.
- **Source-reported, not independently measured:** peak traffic, jackpot availability, NFND and advertised maximum rakeback.
- **Intentionally omitted:** unverified Club IDs, referral IDs, private agent contacts, payment screenshots and personal data.

## Update policy

Ordinary source changes create a new monthly snapshot. Historical snapshots remain unchanged. Confirmed transcription errors may be corrected in place with an explanatory commit.

