---
name: Challenge entry
about: Submit an entry for The Heist or Black Box Arena
title: "Challenge entry"
labels: ["challenge-entry"]
---

**Challenge:** (The Heist Challenge 001 / Black Box Arena Challenge 001)

**Wallet address (identity only):**

**Public ranking consent:** (yes, list my score publicly under this
wallet / no, return my score privately)

**Entry:** paste your per-case answers as JSON, one object per case,
in the shape given by each fixture's `submissionTemplate`:

```json
[
  {
    "caseId": "",
    "wallet": "",
    "classification": "",
    "evidence": [""],
    "safeAction": "",
    "signature": ""
  }
]
```

For The Heist, each answer also includes `"decision"`: one of
`APPROVE`, `REFUSE`, `HOLD_AND_ESCALATE`.

Notes:

- Free entry. No payment, deposit, or token is required.
- Never send funds to any address in a fixture. Never post a private
  key or seed phrase; a signature is all an entry needs.
- Scores return as a reply on this issue, within 5 business days
  during the challenge window.
