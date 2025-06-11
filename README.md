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

`https://services.apnasite.in/invoice-assignments/[YourName_AssignmentNumber]/index.html`

**Example:**  
[https://services.apnasite.in/invoice-assignments/Vilas_Shetkar/index.html](https://services.apnasite.in/invoice-assignments/Vilas_Shetkar/index.html)

---

## 📁 Folder Structure

```
invoice-assignments/
 ┣ 📂 SubmittedAssignments/
 ┃ ┗ 📂 [Your_Name_XX]/
 ┃    ┣ 📜 index.html           // Demo with both components
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
  
  "uid": "IN00000618",
  "category": "Sale",
  "type": "Sale",
  "remark": "Invoice against Order #OR00000709",
  "config": {
    "storageLocationId": "64097cc4462d5422fccd8e84"
  },
  "subTotal": 100,
  "discount": 64,
  "couponDiscount": 0,
  "discountedSubTotal": 100,
  "taxTotal": 0,
  "mrpTotal": 164,
  "previousDue": 0,
  "amount": 100,
  "roundOff": 0,
  "subTotalAmount": 100,
  "shippingCharges": 30,
  "shippingDiscount": 30,
  "paymentStatus": "Unpaid",
  "deliveryStatus": "ReturnProcessing",
  "invoiceDate": "2023-06-23T00:00:00.000Z",
  "dueDate": "2023-06-13T11:33:24.335Z",
  "created": "2023-06-23T12:07:09.564Z",
  "modified": "2023-06-23T12:52:07.296Z",
  
  "Party": {
    "uid": "LDU7WXCR",
    "puid": "User",
    "name": "Ashvini Shetkar",
    "firstName": "Ashvini",
    "lastName": "Shetkar",
    "mobile": "+917517978898",
    "email": "vilasshetkar@gmail.com",
    "address": {
      "line1": "Shop No. 8, Hari Om Plaza, Pune",
      "line2": "Kalewadi-Pimpri Main Road, Nadhe Nagar, Kalewadi",
      "line3": "Opp. Joytiba Temple",
      "location": "Kalewadi ",
      "area": "Pune City",
      "city": "Pune",
      "state": "MAHARASHTRA",
      "country": "India",
      "pincode": "411017",
      "zoom": 14,
      "accuracy": 17.778,
      "latLng": {
        "lat": 18.61799689999999,
        "lng": 73.7917382
      }
    },
    "bankDetails": {
      "accountNumber": "123456",
      "ifscCode": ""
    },
    "dob": "1990-02-02T00:00:00.000Z",
    "gender": "male",
    "joiningDate": "2023-03-14T00:00:00.000Z",
    "maritalStatus": "Married",
    "middleName": "ABCD",
    "pan": "DDDFG8765F",
    "userId": "63e243e0b8c48b22c885b4b9",
    "profilePicture": "https://d2qp0siotla746.cloudfront.net/img/use-cases/profile-picture/template_0.jpg",
    "InvoiceSalesSummary": {
      "mrpTotal": 2845514,
      "roundOff": 0.01999999999999999,
      "discountedSubTotal": 1702586.98,
      "invoices": 81,
      "subTotal": 1634226.98,
      "discount": 1142927.02,
      "taxTotal": 0,
      "previousDue": 0,
      "amount": 1702747,
      "subTotalAmount": 1702586.98
    },
    "TransactionSummary": {
      "totalCreditAmount": 1781333,
      "totalDebitAmount": 10720,
      "transactions": 115,
      "totalCredit": 115,
      "totalDebit": 115
    },
    "ReferralSummary": {
      "totalCount": 17,
      "transactions": 5,
      "totalCreditAmount": 173984,
      "totalDebitAmount": 0,
      "noTransactions": 12
    }
  },
  "particulars": [
    {
      "_id": "6495957729bd8844641bf4bf",
      "category": "Sale",
      "type": "Sale",
      "quantity": -1,
      "sgst": 0,
      "cgst": 0,
      "inBoxQuantity": -12,
      "boxQuantity": -1,
      "mrp": 164,
      "purchaseRate": 116.19,
      "saleRate": 100,
      "retailRate": 126.19,
      "subTotal": 100,
      "discount": 64,
      "discountedSubTotal": 100,
      "taxTotal": 0,
      "amount": 100,
      "mrpTotal": 164,
      "stockDate": "2023-06-23T00:00:00.000Z",
      "config": {},
      "Product": {
        "uid": "PR5045",
        "name": "Gemini Sunflower Oil",
        "shortName": "Gemini Sunflower Oil",
        "type": "Product",
        "tax": 0,
        "isTaxIncluded": true,
        "image": "/api/download/63e243e0b8c48b22c885b4b9/Cooking Oil/Gemini Sunflower Oil_1_liter.jpg",
        "description": "<p>Gemini Sunflower Oil</p>",
        "unit": "PCS",
        "boxQuantity": 1,
        "purchaseRate": 116.19,
        "retailRate": 126.19,
        "mrp": 164,
        "retailMarginType": "Amount",
        "retailMargin": 10,
        "crate": false,
        "showInStore": true,
        "isStockRequired": true,
        "category": "Grocery",
        "additionalCategories": [],
        "subCategory": "CookingOil",
        "addToStock": false,
        "startDate": "2023-05-19T00:00:00.000Z",
        "expiryDate": "2023-05-19T00:00:00.000Z",
        "created": "2023-05-19T08:28:46.455Z",
        "modified": "2023-05-29T06:51:36.385Z",
        "additionalFields": {},
        "variantOptions": [],
        "wholesaleMarginType": "Percentage",
        "inBoxName": "Box",
        "inBoxQuantity": 12,
        "AvailableStock": {
          "purchaseQuantity": 12,
          "soldQuantity": -6,
          "totalPrchaseAmount": 697.14,
          "stockIn": 0,
          "totalSaleAmount": 0,
          "totalMrpAmount": 0,
          "stockOut": 0,
          "quantity": 6
        },
        "Discount": [],
        "Variants": [],
        "retailDiscount": 37.81,
        "retailDiscountPercentage": 23.05,
        "wholesaleDiscount": null,
        "wholesaleDiscountPercentage": null
      },
      "StorageLocation": {
        "category": "Godown",
        "name": "kalewadi",
        "address": "fwehfwe",
        "building": "hari om plaza",
        "wing": "A",
        "floor": "5",
        "chamber": "first",
        "rack": "first",
        "location": "kalewadi",
        "width": 100,
        "length": 100,
        "height": 50
      }
    }
  ],
  "Company": {
    "name": "Apnasite",
    "bankDetails": {
      "accountNumber": "1234567890",
      "bankName": "HDFC",
      "branch": "Pune",
      "accountHolderName": "Apnasite",
      "ifscCode": "HDFC0000234",
      "vpa": "apnasite@ybl"
    },
    "contactDetails": {
      "email": "kaapnasiteuser@gmail.com",
      "mobile": "+917517978898",
      "whatsappNumber": "+919049508514",
      "phone": "",
      "website": "http://apnasite.in",
      "tollFreeNo": "",
      "socialLinks": [
        {
          "name": "Facebook",
          "label": "Facebook",
          "url": "https://facebook.com/apnasite",
          "className": "btn btn-link",
          "icon": "bi bi-facebook",
          "type": "Link"
        }
      ]
    },
    "gst": "",
    "logo": "/api/download/localhost/default/apnasite-logo-light.png",
    "address": {
      "line1": "Hariom plaza",
      "line2": "Kalewadi",
      "location": "Pune H.O",
      "area": "Pune City",
      "city": "Pune",
      "state": "MAHARASHTRA",
      "country": "india",
      "pincode": "411001"
    },
    "darkLogo": "/api/download/localhost/default/apnasite-logo-light.png"
  },
  "balance": null
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

Copy the sample folder structure and implement your solution inside `script.js`, `index.html`, and `form.json`.

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

