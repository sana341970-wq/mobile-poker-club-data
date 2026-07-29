# Security Policy

This is a public data repository and does not contain application code, payment systems or user accounts. Its main security risks are accidental publication of secrets, private access codes or personal data.

## Report privately

Use GitHub's **Report a vulnerability** feature for any issue involving:

- credentials, API keys, tokens or private repository access;
- personal information or private agent contact details;
- a Club ID or referral code that was not already intentionally public;
- a workflow or repository setting that could permit unauthorized changes.

Do not open a public issue containing sensitive material. Include only the minimum information needed to reproduce the problem. Maintainers will acknowledge a valid report as soon as practical and remove exposed material before discussing it publicly.

## Public data corrections

Non-sensitive corrections should use the Data correction issue form. Include the affected field, a public source URL and the observation date.

## Maintainer rules

- Never commit `.env` files, authentication tokens, private screenshots or message histories.
- Do not infer or scrape access credentials that a source intentionally withholds.
- GitHub Actions receive read-only repository permissions.
- Review automated checks before merging changes to the dataset.

Only the latest dataset version and current default branch are supported.

