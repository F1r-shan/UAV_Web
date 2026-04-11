# ✈️ KhachatryanUAV — Precision Aerial Systems

A modern, high-performance landing page for **KhachatryanUAV**, showcasing advanced fixed-wing UAV platforms, engineering philosophy, and a donation system to support development.

---

## 🚀 Overview

This project is a **single-page responsive website** built with pure HTML, CSS, and minimal JavaScript.

It presents:

* UAV company branding
* Aircraft models (Kh-25 & Kh-26)
* Engineering highlights
* Donation interface

Designed with a **dark aerospace-inspired UI**, smooth scrolling, and interactive elements.

---

## 🧩 Features

### 🎯 Core Sections

* **Navigation Bar** (fixed, blur effect)
* **Hero Section** with animated-style SVG drone
* **About Section** (company + engineering pillars)
* **Models Section**

  * Kh-25 (Experimental platform)
  * Kh-26 (Long-range UAV)
* **Donate Section**

  * Funding progress bar
  * Preset + custom donation amounts
  * Multiple payment methods (UI ready)
* **Footer** with branding and contact link

---

## 🎨 Design Highlights

* Fully responsive layout
* Custom CSS variables for theme control
* Smooth scrolling experience
* Clean grid-based structure
* Inline **SVG aircraft illustrations**
* Glassmorphism-inspired navigation bar
* Aerospace-style color palette:

  * Cyan: `#00c8ff`
  * Orange: `#ff6b00`
  * Dark backgrounds

---

## 🛠️ Technologies Used

* **HTML5**
* **CSS3**

  * Flexbox
  * Grid
  * Media Queries
* **Vanilla JavaScript**
* **SVG Graphics (inline)**

---

## 📂 Project Structure

```
project/
│── index.html   # Main website file
```

---

## ⚙️ Functionality

### Donation System (Frontend Only)

* Select preset donation amounts
* Enter custom amount
* Choose payment method:

  * PayPal
  * Cryptocurrency
  * Bank Transfer

⚠️ Note:

> Payment processing is not implemented. You must integrate APIs (Stripe, PayPal SDK, crypto wallets, etc.).

---

## 🧪 Customization Guide

### Change Colors

Edit CSS variables in `:root`:

```css
:root {
  --accent: #00c8ff;
  --accent2: #ff6b00;
}
```

### Update Models

Modify content inside:

```html
<section id="models">
```

### Connect Real Payments

Replace this function:

```javascript
function donate(method) {
  alert("Connect your payment processor here.");
}
```

With:

* PayPal SDK
* Stripe Checkout
* Crypto wallet integration

---

## 📱 Responsiveness

Optimized for:

* Desktop
* Tablet
* Mobile (adaptive layouts below 700px)

---

## 🔮 Future Improvements

* Backend donation processing
* Live telemetry / UAV data dashboard
* CMS integration
* Multi-language support
* Authentication for supporters
* Real flight footage & media gallery

---

## 👤 Author

**Aghavard Khachatryan**
Armenian UAV Engineer

🔗 LinkedIn:
[https://am.linkedin.com/in/aghavard-khachatryan-241246382](https://am.linkedin.com/in/aghavard-khachatryan-241246382)

---

## 📜 License

This project is open for personal and educational use.

For commercial or defense-related applications, please contact the author.

---

## ⚠️ Disclaimer

This website is a **frontend demonstration** of UAV systems and does not include:

* Real UAV control software
* Embedded systems code
* Flight-critical systems

---

## 💡 Final Note

> Built to Fly. Built to Last.

KhachatryanUAV represents a vision of **precision engineering, long-range capability, and independent aerospace innovation**.
