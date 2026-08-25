# EXERCISE IN PROGRESS — Read before editing app code

The user is working through a learning exercise in this codebase (self-study). Do NOT fix the gaps listed below on your own initiative — they ARE the exercise.

- **Exercise spec (for the user):** `EXERCISE.md` — "Wire up the Expense Form (Add + Edit with Validation)"
- **If the user asks for help:** give hints and guidance first, not a full solution, unless they explicitly ask for the solution.
- **If the user asks you to implement it:** confirm with them first, since it defeats the exercise purpose.

## Intentionally incomplete spots (exercise territory)

- `components/ManageExpense/ExpenseForm.js:23` — `submitHandler` is empty; the `onSubmit` prop is declared but never called.
- `screens/ManageExpense.js:40` — `ExpenseForm` is rendered without the `onSubmit` prop.
- `screens/ManageExpense.js:30-37` — `confirmHandler` uses hardcoded test data (`'Test!!!'`, `19.99`, `new Date('2026-08-20')`) instead of form input.
- Form is not prefilled when editing an existing expense.
- No input validation / error messages.

## Other notes

- `store/expenses-context.js:38` — dummy expense `e6` is dated `2026-08-18` so it shows up on the Recent tab (test data).
- The app is based on Maximilian's "The Complete React Developer" expenses tracker (Expo/React Native).
- See `AGENTS.md` for the Expo v57 docs requirement before writing any code.