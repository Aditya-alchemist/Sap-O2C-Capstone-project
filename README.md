# SAP Order-to-Cash (O2C) — Capstone Project

**Student:** Aditya Kumar Mishra  
**Roll Number:** 2304160  
**Batch / Program:** 2023 B.Tech  
**Institution:** KIIT DU  
**Submission Date:** April 21, 2026  
**Module:** SAP SD — Sales & Distribution  

---

## 📋 Project Overview

This capstone project implements a complete **Order-to-Cash (O2C)** business cycle in **SAP S/4HANA** using the **Sales & Distribution (SD)** module.

The O2C cycle covers the full journey of a customer order — from the initial sales inquiry to final payment collection — across three integrated SAP modules: **SD (Sales)**, **MM (Inventory)**, and **FI (Finance)**.

**Fictitious Company:** TechMart Electronics Pvt. Ltd.  
**Company Code:** TMEP | **Sales Org:** TMSO | **Plant:** TMPL | **Currency:** INR

---

## 🔄 O2C Process — 10 Steps Executed

| Step | Transaction | Document Created | Purpose |
|------|-------------|-----------------|---------|
| 1 | VA11 / VA21 | Inquiry / Quotation | Pre-sales, pricing agreement |
| 2 | VA01 | Sales Order (OR) | Customer order committed |
| 3 | CO09 / Auto | Schedule Lines | ATP stock confirmed |
| 4 | VL01N | Outbound Delivery (LF) | Warehouse authorised to ship |
| 5 | LT0A | Transfer Order | Physical picking done |
| 6 | VL02N → PGI | Material Document | Stock reduced, COGS posted |
| 7 | VF01 | Billing Document (F2) | Customer invoice raised |
| 8 | Auto FI | Accounting Document | AR, Revenue, GST posted |
| 9 | F-28 | Clearing Document | Payment received and matched |
| 10 | F150 | Dunning Notice | Overdue collection triggered |

---

## ⚙️ What Was Configured

- Enterprise structure: Company Code, Sales Org, Distribution Channel, Division, Plant, Storage Location
- Customer master (XD01) and Material master (MM01) with all views
- Pricing procedure with PR00 (base price), K004 (discount), MWST (18% GST — CGST + SGST)
- Shipping point determination and delivery document types
- Credit management via FD32 — credit limit check at sales order
- Account determination (VKOA) — Revenue, AR, CGST Payable, SGST Payable
- Output determination — printed invoice, delivery note, order confirmation

---

## 📁 Repository Contents

```
SAP-O2C-Capstone-2304160/
│
├── SAP_O2C_Capstone_Aditya_Kumar_Mishra.pdf   ← Project Report (PDF)
├── SAP_O2C_Capstone_Aditya_Kumar_Mishra.docx  ← Project Report (Word)
└── README.md                                   ← This file
```

---

## 🛠️ Tech Stack

| Component | Details |
|-----------|---------|
| ERP Platform | SAP S/4HANA 2023 |
| Primary Module | SAP SD (Sales & Distribution) |
| Integrated Modules | SAP FI, SAP MM |
| Configuration Tool | SPRO / IMG |
| Tax Configuration | Indian GST — CGST + SGST via MWST |
| Reporting | VA05, VF05, FB03, S_ALR reports |

---

## 📊 Business Impact

| Metric | Before SAP | After O2C |
|--------|-----------|-----------|
| Order-to-Ship Time | 3–5 days | Same day |
| Invoice Error Rate | ~12% | < 1% |
| Days Sales Outstanding | 45+ days | 22 days |
| GST Compliance | Manual | Automated |

---

## 📌 Key Unique Points

1. **Indian GST** — CGST + SGST tax configuration for Indian intra-state transactions
2. **Full Document Chain** — Inquiry → Quotation → SO → Delivery → PGI → Invoice → Payment, all linked
3. **Credit Management** — Live credit check preventing overselling to high-risk customers
4. **Return Order Cycle** — Document type RE and credit memo G2 configured for reverse flow
5. **Three-way FI-MM-SD Integration** — PGI automatically posts COGS and reduces inventory

---

*Individual project submitted for KIIT DU Capstone Assessment, April 2026.*
