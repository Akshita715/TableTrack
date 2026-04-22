# 🍽️ Aim Software — Restaurant POS System

> **"Your Business, Perfected."**
> A fully functional, browser-based Restaurant Point-of-Sale system built with pure HTML, CSS (Tailwind), and Vanilla JavaScript.

---

## 👩‍💻 Developed By

**Akshita Joshi** — Handcrafted with dedication.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [How to Run](#how-to-run)
- [Module Breakdown](#module-breakdown)
- [Menu Categories](#menu-categories)
- [Data & Storage](#data--storage)
- [Screenshots](#screenshots)

---

## 🧾 Overview

**Aim Software** is a complete restaurant management solution that runs entirely in the browser — no backend, no database setup, no installation required. Just open the HTML file and you're ready to take orders.

It simulates a real-world restaurant workflow: from taking a new order at the POS terminal → sending it to the kitchen (KDS) → generating a bill → marking payment → saving daily reports.

---

## ✨ Features

### 🖥️ Dashboard
- Live summary of the day's revenue, total orders, occupied tables, and stock alerts
- Filter orders by any date
- View recent order feed with timestamps
- Live table status grid (color-coded)
- Save day's sales report and reset for a new day

### 🛒 New Order (POS)
- Category-wise menu navigation
- Item cards with images and prices
- Real-time availability check (items go "Out of Stock" automatically based on inventory)
- Add/remove items with quantity control
- Discount support (%)
- Customer name, mobile number, and table assignment
- KOT (Kitchen Order Ticket) generation

### 🪑 Table Management
- 20 tables displayed in a grid
- Color-coded status: 🟢 Available / 🔵 Occupied / 🟡 Reserved
- Click any table to update its status
- Tables automatically become occupied when an order is placed and free up after payment

### 👨‍🍳 KDS (Kitchen Display System)
- Live view of all active kitchen orders
- Audio alert for new incoming orders
- Mark individual items as "Done"
- Mark entire orders as "Served"
- Flash animation for new orders

### 💳 Billing
- Full billing history with search (by Order ID or Customer Name)
- View itemized bill in a modal
- Mark unpaid orders as Paid (Cash or UPI)
- Download bill as a `.txt` file

### 📦 Inventory Management
- 29 inventory items tracked with current stock and units
- Low stock alerts (highlighted in red)
- Update stock quantities inline

### 👥 Staff Management
- View all staff with role, shift, and salary
- Add new staff members
- Edit existing staff details

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 | Structure |
| Tailwind CSS (CDN) | Styling & Layout |
| Phosphor Icons | Icons |
| Google Fonts (Poppins) | Typography |
| Vanilla JavaScript (ES Modules) | All logic & state |
| localStorage | Data persistence across sessions |

**No frameworks. No build tools. No dependencies to install.**

---

## 🚀 How to Run

1. **Download** the `index.html` file.
2. **Open** it in any modern browser (Chrome, Firefox, Edge).
3. That's it. ✅

> Works completely offline after the initial CDN load (Tailwind, Phosphor Icons, Google Fonts).

---

## 📁 Module Breakdown

```
index.html
│
├── AppState              → Global state (menu, tables, orders, inventory, staff)
├── generateMockMenu()    → Creates full menu with inventory linkage
├── loadData()            → Loads saved data from localStorage
├── saveData()            → Persists state to localStorage
│
├── RENDER FUNCTIONS
│   ├── renderDashboard()
│   ├── renderNewOrderView()
│   ├── filterPosMenuByCategory()
│   ├── renderPosBill()
│   ├── renderTables()
│   ├── renderKDS()
│   ├── renderBilling()
│   ├── renderInventory()
│   ├── renderStaff()
│   └── renderBillModal()
│
└── EVENT HANDLERS
    ├── handleAddItemToCurrentOrder()
    ├── handleUpdateQtyInOrder()
    ├── confirmBillGeneration()
    ├── handleMarkItemDone()
    ├── handleMarkOrderServed()
    ├── confirmPayment()
    ├── handlePrintBill()
    ├── handleUpdateStock()
    ├── handleStaffFormSubmit()
    ├── handleTableCardClick()
    ├── handleTableStatusChange()
    ├── saveDailyReport()
    └── handleDownloadReport()
```

---

## 🍕 Menu Categories

The system comes pre-loaded with a full Indian café/restaurant menu:

| Category | Sample Items |
|---|---|
| ☕ Chai & Coffee | Masala Chai, Hot Coffee, Black Coffee |
| 🥤 Mocktails & Frappes | Virgin Mojito, Cold Coffee Frappe |
| 🧃 Soft Drinks & Water | Coke/Pepsi, Fresh Lime Soda, Mineral Water |
| 🍲 Soups | Tomato Soup, Manchow Soup, Hot & Sour Soup |
| 🍟 Starters & Fries | Paneer Tikka, Momos, French Fries, Veg Patties |
| 🍜 Maggie | Classic Masala, Vegetable, Cheese Maggie |
| 🍝 Noodles & Pasta | Hakka Noodles, Alfredo Pasta, Arrabbiata Pasta |
| 🥪 Sandwich & Toast | Grilled Sandwich, Cheese Toast, Paneer Sandwich |
| 🍕 Pizza (8 inch) | Margherita, Veggie Delight, Paneer Tikka |
| 🌯 Rolls | Veg Roll, Paneer Roll, Chilli Paneer Roll |
| 🥗 Salads | Green Salad, Russian Salad |

---

## 💾 Data & Storage

All data is saved in the browser's **localStorage** under these keys:

| Key | Contents |
|---|---|
| `aim-pos-orders` | All orders (JSON array) |
| `aim-pos-reports` | Saved daily reports (JSON object) |
| `aim-pos-nextOrderId` | Auto-increment order counter |
| `aim-pos-last-date` | Last active date (for auto-report trigger) |

> **Note:** Clearing browser data / localStorage will reset all orders and reports. Download reports regularly using the Dashboard.

---

## 🔄 Order Workflow

```
New Order (POS)
    ↓
Customer Details + Table Assignment
    ↓
KOT Sent → KDS (Kitchen Display System)
    ↓
Kitchen marks items Done → Order marked Served
    ↓
Billing View → View Bill Modal
    ↓
Mark as Paid (Cash / UPI)
    ↓
Table freed → Dashboard updated
```

---

## 📊 Inventory-Menu Linkage

Every menu item is linked to raw inventory. When an order is placed, the system **automatically deducts** ingredient quantities from stock. If an ingredient runs out, the menu item is automatically marked **"Out of Stock"** in the POS view.

Example:
- **Paneer Tikka** uses `0.2 kg Paneer` + `0.1 kg Yogurt` per serving
- **Classic Masala Maggie** uses `1 Maggi Packet` per serving

---

## 📌 Known Limitations

- Data is browser-local only (no cloud sync or multi-device support)
- No user login / role-based access control
- Reports are downloaded as `.txt` files (no PDF)
- No network/server required — fully client-side

---

## 🙌 Credits

Built entirely from scratch by **Akshita Joshi**.
Powered by open-source tools: Tailwind CSS, Phosphor Icons, Google Fonts.

---

*Aim Software — Simple. Fast. Reliable.*
