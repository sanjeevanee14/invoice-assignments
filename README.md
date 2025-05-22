# 🧾 JavaScript Invoice Assignment using Web Components

## 📌 Project Overview

This project is developed and maintained by **Maha Mission Education and Career Council (NGO)** under its skill-based learning initiative at **ApnaGuru.in**. The assignment is technically supported by **Apnasite IT Services Pvt. Ltd.**, providing:

✅ **Frontend training and mentorship**  
✅ **Deployment and versioning**  
✅ **Ongoing platform maintenance**

**🌐 Live Preview:**  
[https://invoice.apnasite.in](https://invoice.apnasite.in)  
**🧑‍🏫 Learn with Us:** [https://apnaguru.in](https://aapn.in/M7PM3JB5)  
**📢 NGO Info:** [https://mmeac.org](https://mmeac.org)  
**🏢 Company:** [https://apnasite.in](https://apnasite.in)  
**📞 Contact:** +91-8999417889 (Call/WhatsApp)

---

## 🧭 Goal

Build a **custom Invoice Application** using two Web Components:

1. `<invoice-component>`: Displays the invoice view.
2. `<invoice-form-component>`: Provides a form to input invoice data.

On submitting the form, the invoice view should update with the user input, demonstrating dynamic data binding between the two components.

**Key Requirements:**

* ✅ **JavaScript’s DOM API** only (no external frameworks)
* ✅ **Web Components** (using `class extends HTMLElement`)
* ✅ **Dynamic `config` and `data` attributes** for styling and content
* ✅ **Reusable structure** for any invoice scenario
* ✅ **Custom event communication** between form and view

---

## 🔗 Deployment Format

`https://services.apnasite.in/invoice-assignments/[YourName_AssignmentNumber]/preview.html`

**Example:**  
[https://services.apnasite.in/invoice-assignments/Mahesh_Bhosle_21/preview.html](https://services.apnasite.in/invoice-assignments/Mahesh_Bhosle_21/preview.html)

---

## 📁 Folder Structure

```
invoice-assignments/
 ┣ 📂 SubmittedAssignments/
 ┃ ┗ 📂 [Your_Name_XX]/
 ┃    ┣ 📜 preview.html           // Demo with both components
 ┃    ┣ 📜 script.js              // JS for <invoice-component> & <invoice-form-component>
 ┃    ┣ 📜 data.json              // Sample JSON for 'data' and 'config'
 ┃    ┣ 📂 IMG/                   // Images and assets (e.g., logos, QR)
 ┃    ┣ 📂 css/                   // Custom CSS (if required)
 ┃    ┗ 📂 fonts/                 // Fonts (optional)
```

---

## 🧱 Component Specifications

### 🔸 `<invoice-component>` Web Component

A full-featured invoice view that dynamically displays:

* 🏢 Company Details (name, GST, address, logo, QR)
* 🧾 Invoice Details (number, date, due date, PO, etc.)
* 👤 Customer Billing & Shipping Info
* 📦 Itemized Table (item, HSN, rate, qty, tax, amount)
* 💰 Total Amount (in words)
* 🏦 Bank Details
* 📄 Terms & Conditions
* 🖊️ Footer (signature, date)

#### Attributes Accepted:

- `data`: JSON structure for invoice content (see example below)
- `config`: Optional JSON for UI customization (class names, etc.)

### 🔸 `<invoice-form-component>` Web Component

A form for entering invoice details. On submit, it dispatches a custom event with the form data, which updates the `<invoice-component>`.

* Fields: Invoice date, number, company, supplier, PO, godown, CST/IGST, etc.
* Can be extended for more fields as needed.

---

## 🎯 Functional Features

* 🧩 Fully encapsulated components using Shadow DOM
* ⚙️ Customization via `data` and `config` JSON
* 🔄 Live rendering on attribute change (`observedAttributes`)
* 🔗 Communication via custom events (`submit`)
* 📦 Optional Bootstrap or custom CSS for styling

---

## 🧪 Example `data` Structure

```json
{
    "companyName": "TATA Technologies",
    "gstNo": "27AAKCS1234H1Z5",
    "title": "Tax Invoice",
    "invoiceNumber": "INV-123456",
    "invoiceDate": "2023-10-01",
    "dueDate": "2023-10-15",
    "poNumber": "PO-456789",
    "logo": "./IMG/tata.png",
    "qr": "./IMG/qr.png",
    "companyAddress": [
        "City: Pune",
        "State: MAHARASHTRA",
        "Country: India",
        "Pincode: 411018",
        "Mobile: 9999999999",
        "Email: Swipe@getswipe.in",
        "Website: www.getswipe.in"
    ],
    "customer": {
        "billing": {
            "name": "Natarajan Chandrasekaran",
            "address": [
                "City: Nanakramguda",
                "State: TELANGANA",
                "Country: INDIA",
                "Pincode: 500032",
                "Email: natrajan@gmail.com",
                "Ph: 9999999999"
            ]
        },
        "shipping": {
            "name": "Natarajan Chandrasekaran",
            "address": [
                "Survey 115/1, ISB Rd, Financial District",
                "Gachibowli, Nanakramguda",
                "City: Nanakramguda",
                "State: TELANGANA",
                "Country: INDIA",
                "Pincode: 500032",
                "Email: natrajan@gmail.com",
                "Ph: 9999999999"
            ]
        }
    },
    "items": [
        {
            "item": "Tata Nexon",
            "hsn": "87038070",
            "rate": "8,05,000.00",
            "qty": 1,
            "taxAmount": "1,44,900.00 (18%)",
            "amount": "9,49,900.00"
        },
        {
            "item": "Car accessories Kit",
            "hsn": "87089900",
            "rate": "2,117.80",
            "qty": 1,
            "taxAmount": "381.20 (18%)",
            "amount": "2,499.00"
        }
    ],
    "bankDetails": {
        "bank": "YES BANK",
        "account": "66789999922445",
        "ifsc": "YESB0BNA567",
        "branch": "Kodihalli"
    },
    "terms": [
        "Terms: Goods once sold cannot be taken back or exchanged."
    ],
    "totalAmountInWords": "INR Nine Lakh, Fifty-Two Thousand, Three Hundred And Ninety-Nine Rupees Only."
}
```

---

## 🧾 `form.json` Structure

Use `form.json` to define a **Formly-compatible** input form for invoice fields and config options.

---

## 🧪 Example `index.html` Usage (Component Integration)

Here’s how to use both components in a regular HTML file and connect them with JavaScript:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Invoice Assignment Demo</title>
    <!-- Optionally include CSS here -->
</head>
<body>
    <!-- Use custom elements directly in HTML -->
    <invoice-form-component id="invoiceForm"></invoice-form-component>
    <invoice-component id="invoiceView"></invoice-component>

    <script src="script.js"></script>
    <script>
        // Get references to the components
        const form = document.getElementById('invoiceForm');
        const invoice = document.getElementById('invoiceView');

        // Listen for the custom 'submit' event from the form component
        form.addEventListener('submit', (event) => {
            // Update the invoice component with new data
            invoice.setAttribute('data', JSON.stringify(event.detail));
        });

        // Optionally, set initial data/config if needed
        // invoice.setAttribute('data', JSON.stringify(initialData));
        // invoice.setAttribute('config', JSON.stringify(initialConfig));
    </script>
</body>
</html>
```

This approach lets you use `<invoice-form-component>` and `<invoice-component>` as regular HTML elements. The JavaScript connects them by listening for the form’s `submit` event and updating the invoice view accordingly.

---

## 🚀 Submission Process

### 1. 📦 Fork the Repository

👉 [https://github.com/Apnasite/invoice-assignments](https://github.com/Apnasite/invoice-assignments)

### 2. 💻 Clone Your Forked Repo

```bash
git clone https://github.com/YOUR_USERNAME/invoice-assignments.git
```

### 3. 🧩 Create Your Assignment Folder

```bash
mkdir SubmittedAssignments/Your_Name_01
```

### 4. 🛠️ Copy and Build

Copy the sample folder structure and implement your solution inside `script.js`, `preview.html`, and `form.json`.

### 5. ✅ Commit and Push

```bash
git add .
git commit -m "Added Invoice Assignment - Your_Name_01"
git push origin main
```

### 6. 🔃 Create Pull Request

After pushing your changes to your forked repository:

1. Go to your forked repository on GitHub.
2. Click the **"Compare & pull request"** button, or go to the "Pull requests" tab and click **"New pull request"**.
3. Set the base repository to `Apnasite/invoice-assignments` and the base branch to `main`.
4. Compare with your fork and branch containing your assignment.
5. Add a clear title and description for your PR (e.g., "Added Invoice Assignment - Your_Name_01").
6. Review your changes, then click **"Create pull request"**.

Your submission will be reviewed and feedback will be provided if needed.

