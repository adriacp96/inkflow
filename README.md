<div align="center">
  <h1>🖋️ INKFLOW</h1>
  <p><strong>A minimalist, robust, and highly visual personal finance tracker.</strong></p>
</div>

---

## 📖 Overview

**INKFLOW** is a beautifully designed, single-page web application built to help you master your cash flow. Featuring a stark, high-contrast, black-and-white aesthetic (with automatic Dark Mode support), INKFLOW lets you effortlessly track your fixed expenses, manage credit card debts, and visualize your financial intensity across a dynamic monthly calendar.

With built-in multi-currency support and seamless cloud synchronization powered by Supabase, INKFLOW gives you a clear snapshot of your financial health at any given moment.

## ✨ Key Features

### 💱 Multi-Currency & Global Tracking
- Natively track expenses in **AED**, **EUR**, and **IDR**.
- Dashboards and visual bar charts automatically break down total debt vs. monthly payments per currency.

### 📅 Dynamic Financial Calendar
- **Intensity Heatmap:** Calendar days automatically shade darker based on the volume of payments due, letting you spot high-expense days at a glance.
- **Daily Breakdowns:** Tap on any calendar day to see a detailed, currency-specific breakdown of exactly what is being charged.

### 💳 Credit Card Management
- Track both **Total Debt** and **Monthly Minimums**.
- **Billing Cycles:** Easily shift a card's charge cycle between "This Month" and "Next Month" to accurately forecast upcoming payments.

### 🔄 Fixed Expenses & Loans
- Track subscriptions, utility bills, insurance, and custom categories.
- **Advanced Loan Tracking:** Enter start and end dates for loans to automatically calculate and display installment progress (e.g., `Installment 5/36`).
- **Flexible Frequencies:** Support for non-monthly recurring payments (e.g., bi-monthly, quarterly, or specific months of the year).

### ☁️ Cloud Sync (Supabase)
- Automatic, non-intrusive cloud saving ensures you never lose your data.
- Effortlessly navigate back and forth through years and months, instantly loading historical financial snapshots.

### 📊 Export & Accessibility
- **Local Backups:** Instantly export your entire active snapshot to JSON via the sticky "Export" button.
- **Keyboard Navigation:** Navigate seamlessly between months using the `Left Arrow` and `Right Arrow` keys.

### 🌗 Clean & Responsive UI
- A utilitarian, print-inspired design language.
- Fully responsive layout that looks great on both mobile and desktop.
- Automatic system **Dark Mode** support.

---

## 🚀 Getting Started

### Prerequisites
All you need is a modern web browser. INKFLOW runs entirely on the client-side with vanilla HTML, CSS, and JavaScript. 

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/inkflow.git
   cd inkflow
   ```

2. **Configure Supabase (Cloud Sync):**
   To enable cloud saving, you need a Supabase project. 
   - Go to Supabase and create a new project.
   - Create a table named `fin_snapshots` with the following columns:
     - `year` (int)
     - `month` (text)
     - `cards` (jsonb)
     - `fixed` (jsonb)
     - `categories` (jsonb)
     - `updated_at` (timestamp)
   - Set the Primary Key / Unique Constraint to a composite of `year` and `month`.
   - Open `index.html` and update the constants with your credentials:
     ```javascript
     const SUPABASE_URL = "https://your-project.supabase.co";
     const SUPABASE_ANON_KEY = "your-anon-key";
     ```

3. **Run the App:**
   Simply open `index.html` in your favorite web browser. No build steps or bundlers required!
   ```bash
   open index.html
   ```

---

## 🛠️ Tech Stack

- **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6+).
- **Backend/Database:** Supabase (PostgreSQL & REST API).
- **Design:** Custom CSS utilizing native CSS variables, CSS Grid, Flexbox, and Media Queries for dark mode styling.

---

## 💡 Usage Guide

1. **Navigate Time:** Use the top bar to select the Year and Month. Data will automatically fetch from the cloud.
2. **Add a Card/Expense:** Scroll to the respective sections, open the `+ New` dropdown, fill in your details (Amount, Currency, Day of Month), and hit Add.
3. **Edit Mode:** Click the `✎ Edit` button floating at the bottom right to toggle editing capabilities. This reveals controls to tweak balances, days, categories, or delete items.
4. **View Breakdowns:** Check the "Actual Payments" section to see your top-level totals, your debt-to-payment ratio bars, and your interactive calendar heatmap.

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
