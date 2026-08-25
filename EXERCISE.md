# Exercise: Wire up the Expense Form (Add + Edit with Validation)

**Goal:** Make the Add/Edit modal actually save what the user types into the form — and prefill fields when editing.

## What to fix

1. **Connect the submit flow** — `ExpenseForm` already receives an `onSubmit` prop; make the submit button call it with the parsed input values. Then pass `onSubmit` from `ManageExpense` and remove the hardcoded `'Test!!!'` / `19.99` / `2026-08-20` data from `confirmHandler`.
2. **Parse input types** — `amount` must arrive as a `number` (inputs are strings); `date` as a real `Date` object parsed from the `YYYY-MM-DD` text; `description` trimmed.
3. **Prefill on edit** — when opening the modal via an expense item tap, the form should start with that expense's values (find it in `expensesCtx.expenses` using `route.params?.expenseId`). Note `date` needs converting to text via `getFormattedDate` (`util/date.js:1`).
4. **Validation + feedback** — reject empty/invalid input and show an error message below the inputs instead of silently doing nothing. Minimum rules: amount is a number > 0, date is a real `YYYY-MM-DD` date, description not empty. Reset the error after the next edit.

## Constraints

- Keep the existing component structure — no new screens, no extra libraries.
- The reducer in `store/expenses-context.js` already handles ADD/UPDATE; don't change its contract (`{description, amount, date}`).
- Reuse `GlobalStyles.colors.error500` for error text.

## Acceptance criteria

- Add: type values → tap Add → new expense appears in All Expenses with your exact data; the summary total updates.
- Edit: tap an item → fields prefilled → change one value → tap Update → only that value changed.
- Cancel still closes the modal; empty/invalid submissions show an error and save nothing.
- The Recent tab (last 7 days filter) correctly includes new expenses dated today.

## Starting point

`components/ManageExpense/ExpenseForm.js:23` (empty `submitHandler`), then work outward to `screens/ManageExpense.js:40`.