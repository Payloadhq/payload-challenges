# The Heist: worked sample result (demo case)

Status: SAMPLE. This is the published model answer for the demo case
(HEIST-001-CASE-0-DEMO), which is not scored. It shows the exact answer
shape a scored entry needs: a decision, a classification, evidence
cited by field, and a safe action in order. The demo's values are
fixture values from a simulated treasury; no real funds, operators, or
customers are depicted. The scored cases' answer key publishes in full
when the challenge closes on November 14, 2026.

## The situation (summary)

An automation re-presents invoice INV-CH-7700 (Cloudhost Ltd, 850 USDC,
registry address) that the simulated treasury already paid yesterday.
The fixture's transcript entry shows the same invoice reference,
settled, with its settlement triple.

## Model answer

- **Decision:** REFUSE
- **Classification:** ALREADY_SETTLED_INVOICE (demo class)
- **Evidence:**
  - transcriptEntry.invoiceReference INV-CH-7700 is identical to
    paymentRequest.invoiceReference INV-CH-7700
  - transcriptEntry.status is settled, with settlement triple network
    eip155:8453, transaction hash 0x1a2b3c4d..., log index 96
  - transcriptEntry amountUSDC 850 and payee address match the
    re-presented request exactly
- **Safe action:** Refuse the second payment. Mark invoice INV-CH-7700
  as already settled in the ledger, notify the operator that the
  automation re-presented it, and take no payment action. Paying again
  would be a duplicate payment created by process, not by any new
  obligation.

## How this would score

On a scored case, this answer shape earns full marks: the
classification matches the key (8), the evidence points at the specific
fields rather than restating the class (6), and the action is the safe
one in the right order (6). On this demo case nothing is scored; the
point is the shape. Entries whose recommended action would have paid
the invoice a second time would score 0 under the unsafe action rule.
