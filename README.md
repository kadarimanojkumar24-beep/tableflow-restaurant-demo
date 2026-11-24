# TableFlow

A lightweight, no-backend restaurant management demo: customers scan a table QR code, browse the menu, order, track food, then see their bill with a tip option and pay. Waiter, kitchen and manager each have their own screen.

## Views

| File | Role | What it does |
|---|---|---|
| `customer.html` | Customer | Opens from the table QR (`customer.html?table=3`). Menu, cart, order tracking, bill, tip, pay |
| `waiter.html` | Waiter | Accepts or rejects requests with an ETA, serves ready orders, confirms payments, seats and clears tables |
| `kitchen.html` | Kitchen | Shows accepted orders: start preparing, delayed, ready |
| `manager.html` | Manager | Overview, table map, QR code generator, orders, menu, staff, cashier report, settings |
| `index.html` | Launcher | Links to the four views |

## Order flow

QR scan (table marked occupied, waiter alerted) → customer orders → waiter accepts + sets ETA → kitchen prepares → ready → waiter serves → bill shown to customer with tip → customer pays → waiter confirms → table cleared.

## Run locally

Open `index.html` in a browser, and open the other views in separate tabs of the **same browser**. Data is shared through `localStorage` and syncs live between tabs. Use "Reset demo" to clear it.

## Host it (for real QR scanning)

1. Repo → Settings → Pages → deploy from the `main` branch, root folder.
2. Open `manager.html` → QR Codes. The URL box is filled with your hosted `customer.html` address; print the codes.

## Limitations

- Demo only: data lives in each browser, so phones and the waiter's device will **not** share data without a backend (planned: Firebase/Supabase).
- Payments are recorded manually by the waiter; UPI only opens a pay link and nothing is verified.
- GST and service charge are configurable inputs, not tax advice.

## License

MIT
