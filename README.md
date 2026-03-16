# 📲 WhatsApp Bulk Report Sender

> A free, local Streamlit web app that lets professors send **personalised WhatsApp reports** to parents — no paid API needed.

---

## 🚀 Quick Start

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Run the app

```bash
streamlit run app.py
```

The app will open automatically in your default browser at `http://localhost:8501`.

---

## 📋 How It Works

| Step | What to do |
|------|-----------|
| **1** | Upload your `.xlsx` or `.csv` file containing student data |
| **2** | Build your message template — click column buttons to insert `{Variables}` |
| **3** | Select which column holds the **Parent's Phone Number** |
| **4** | Review the **live preview** with the first student's data |
| **5** | Click **Send All Reports** — the app loops through every row and sends a personalised WhatsApp message |

---

## 📊 Required Spreadsheet Format

Your file must have **column headers** in the first row. Example:

| Student_Name | Python_Marks | Maths_Marks | Attendance | Parent_Phone |
|---|---|---|---|---|
| Alice Sharma | 88 | 92 | 92% | +919876543210 |
| Bob Khan | 74 | 68 | 85% | +919988776655 |

- **Phone numbers** must include the country code (e.g., `+91` for India).
- Column names can be anything — they become template variables.

---

## ✍️ Template Example

```
Dear Parent of {Student_Name},

Here is the performance report for this semester:

  • Python Programming : {Python_Marks}
  • Mathematics        : {Maths_Marks}
  • Attendance         : {Attendance}

Please contact the institution if you have any queries.

Regards,
Prof. Sharma
```

---

## ⚙️ Safety & Anti-Ban Measures

- **15-second browser open delay** — gives WhatsApp Web time to load before typing.
- **20-second gap** between each message — prevents rate-limiting / bans.
- **Tab auto-closes** after each message is sent.

> ⚠️ **Important:** Make sure **WhatsApp Web** is already logged in at [web.whatsapp.com](https://web.whatsapp.com) in your default browser **before** clicking Send.

---

## 🛠️ Tech Stack

| Library | Purpose |
|--------|---------|
| `streamlit` | Web UI framework |
| `pandas` | Excel/CSV parsing |
| `openpyxl` | `.xlsx` file support for pandas |
| `pywhatkit` | WhatsApp Web automation |

---

## ⚠️ Disclaimer

This tool automates the browser using `pywhatkit`. It is intended for legitimate, low-volume academic reporting. Sending bulk spam messages is against WhatsApp's Terms of Service. Use responsibly.
