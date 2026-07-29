# Methodology

## Scope

This repository records public listing data for clubs shown in the English-language Poker Catalog directory. The dataset is descriptive: inclusion means that a listing was present at observation time, not that this repository independently guarantees a club, rate, traffic level or transaction.

## Collection

For the 2026-07 snapshot, the catalog index and each club page were observed on 2026-07-29 in Asia/Bangkok time. Application comparison pages were checked the same day.

Each record is transcribed from these public fields:

- app, club name and union;
- public Club ID status;
- advertised maximum rakeback;
- reported peak traffic;
- games, stakes and countries;
- jackpot availability and listing update date;
- NFND badge on the catalog card.

## Normalization rules

- Percentages are integers without a percent sign.
- En dashes in traffic ranges are normalized into numeric `min_players` and `max_players` fields while preserving the original `display` value.
- A trailing plus sign sets `open_ended` to `true`.
- Multi-value CSV fields use a pipe (`|`) separator.
- `club_id` stays `null` when the source does not publish an ID.
- Game labels are normalized to uppercase source abbreviations, for example `PLO4`, `PLO5`, `AOF` and `MTT`.
- NFND is `true` only when explicitly displayed on the current catalog card.

## Limitations

Traffic and commercial terms can change faster than the monthly publication cycle. Reported player ranges are not independently audited live counts. Rake structures are club-defined and may vary by table, stake and union, so the app comparison does not assign one universal rake model.

## Corrections

Proposed corrections should identify the field, public source URL, observation date and replacement value. Historical snapshots are not rewritten for ordinary changes; corrections to transcription errors may be made with an explanatory commit.

