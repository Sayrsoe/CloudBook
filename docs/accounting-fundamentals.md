# Accounting Fundamentals — Research Notes

> Project: CloudBook SaaS | Reference: Manager Cloud screenshots | Updated: 2026-11-04
>
> Beginner notes for product research and software design. Not tax or accounting advice.

## 1. Five core accounting terms

| Term | Meaning | Example |
| --- | --- | --- |
| Asset | Resource controlled by the business | Cash, inventory, equipment |
| Liability | Amount the business owes | Loan, unpaid supplier bill |
| Equity | Owner's residual interest | Capital, retained earnings |
| Revenue | Income earned from business activity | Website design fee |
| Expense | Cost of running the business | Rent, software subscription |

**Accounting equation:** Assets = Liabilities + Equity.

**Profit (simplified):** Revenue − Expenses. For product businesses, cost of goods sold is an important expense category.

## 2. Important transactions

- **Sales invoice:** Request for payment after selling goods or services; may create accounts receivable.
- **Receipt:** Records money received, often against an unpaid invoice.
- **Purchase invoice:** Supplier bill; may create accounts payable.
- **Payment:** Records money paid to a supplier or for an expense.
- **Transfer:** Moves money between the business's own bank/cash accounts; not revenue or expense by itself.
- **Journal entry:** Records accounting changes using balanced debits and credits.

## 3. Double-entry bookkeeping

Each journal entry has equal total debits and credits. Debit and credit do **not** simply mean money in and money out.

Example: invoice a client $100, then receive $100:

| Event | Debit | Credit |
| --- | --- | --- |
| Issue invoice | Accounts Receivable $100 | Service Revenue $100 |
| Receive payment | Bank $100 | Accounts Receivable $100 |

The receipt settles the receivable; it must not record the same $100 as revenue again. This example assumes accrual accounting.

## 4. Financial reports

- **Balance sheet:** Assets, liabilities and equity at a specific date.
- **Profit and loss (income statement):** Revenue and expenses over a period.
- **Cash flow statement:** Cash movements from operating, investing and financing activities over a period.
- **Accounts receivable:** Money customers owe.
- **Accounts payable:** Money the business owes suppliers.

## 5. Features observed in the reference software

The screenshots show business selection, dashboard/summary, bank and cash accounts, receipts, payments, transfers, customers, sales invoices, suppliers, purchase orders/invoices, inventory, employees, payslips, fixed assets, journal entries, reports, and settings. Some advanced settings include chart of accounts, user permissions, recurring transactions, and starting balances.

These are **observed UI labels**, not a verified inventory of all capabilities.

## 6. Design rules for our SaaS

1. Every business record belongs to a tenant/business; enforce authorization on the backend.
2. Store money using fixed-precision decimal values or integer minor units, not binary floating-point.
3. Keep invoice status and payment allocation consistent; prevent double counting.
4. Use database transactions for changes that must succeed or fail together.
5. Preserve an audit trail for sensitive financial edits and corrections.
6. Support backups and recovery; do not rely only on a dashboard total.
7. Make common freelancer workflows simple; reveal advanced accounting features only when needed.
8. Handle currency, rounding, tax and local regulations explicitly before international rollout.

## 7. Suggested MVP scope

Start with authentication, business workspace, clients, invoices, manual payment tracking, expenses and basic reports. Research accounting requirements before claiming full bookkeeping or tax compliance. Inventory, payroll and advanced accounting can be considered later.

## 8. Open research questions

- Which accounting basis (cash or accrual) will our first product support?
- Which countries and currencies will be supported first?
- How will refunds, partial payments and invoice cancellations work?
- Which features do freelancers actually need and want to pay for?
