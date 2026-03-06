---
title: "Intercompany Elimination: The Step Most Teams Get Wrong"
description: "How intercompany eliminations work in consolidation, common mistakes, and how to automate the most error-prone step in month-end close."
date: 2026-02-12
---

## Why intercompany elimination matters

When Entity A sells $100K of services to Entity B, the group's consolidated revenue should not increase by $100K. That's internal activity, not real revenue.

Intercompany elimination removes these internal transactions so the consolidated financials reflect only external activity. Get it wrong, and you overstate revenue, inflate assets, or misrepresent the group's financial position.

## The manual process

Most teams do IC elimination in Excel:

1. Export trial balances from all entities
2. Manually identify intercompany accounts (usually by naming convention - "IC Receivable", "Due from Entity B")
3. Create elimination journal entries
4. Post them to the consolidation workbook
5. Verify the eliminations balance to zero

The problems:

- **Naming conventions vary**: Entity A uses "IC-Receivable", Entity B uses "Due from Parent", Entity C uses "Interco AR"
- **Amounts don't match**: Entity A booked $50,000 but Entity B booked $49,850 due to timing or FX
- **New IC relationships appear**: An acquisition adds Entity D, and nobody updates the elimination template

## Common mistakes

### Missing one side
Entity A's IC payable gets eliminated, but Entity B's corresponding IC receivable doesn't. The balance sheet is off, and the error is buried in a 500-row trial balance.

### Wrong exchange rate on IC
Entity A records the transaction in USD, Entity B records it in EUR. If the elimination uses a different rate than either entity used, you create a phantom FX gain/loss.

### Stale templates
The elimination template was built for 3 entities. After acquiring Entity D six months ago, someone forgot to add it. Entity D's IC transactions pass through uneliminated.

## How automated IC detection works

Instead of relying on naming conventions, automated detection uses multiple signals:

1. **Account name patterns**: keywords like "intercompany", "IC", "due from", "due to", "inter-entity" in any language
2. **Entity prefixes**: account codes starting with another entity's identifier (e.g., Entity A's trial balance containing accounts prefixed "B-")
3. **Amount matching**: cross-entity amounts that offset within a tolerance (catches timing differences)

The tool flags potential IC relationships and generates elimination entries. You review and confirm - the judgment stays with you, but the detective work is automated.

## The elimination journal

A proper IC elimination produces a formal journal with:

- Debit and credit entries that net to zero
- Reference to the source accounts in each entity
- The exchange rate applied (if cross-currency)
- The variance, if the two sides don't match exactly

This journal is your audit trail. When the auditor asks "why did you eliminate this $200K?", you point to the matching accounts in Entity A and Entity B's trial balances.

## Reducing IC mismatches

The best way to reduce elimination headaches is to reduce IC mismatches at the source:

- **Standardize IC account naming** across entities (even if ERPs differ)
- **Reconcile IC balances monthly** before close (don't let mismatches accumulate)
- **Use a common currency** for IC transactions where possible

But even with perfect discipline, you still need a tool that catches what humans miss. [Try the demo](https://app.accounting-bridge.com/demo) with multi-entity files to see IC detection in action.
