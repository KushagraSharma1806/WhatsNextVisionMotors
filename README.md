# 🚗 WhatsNext Vision Motors CRM (Salesforce Project)

A full-featured Salesforce CRM solution designed for vehicle dealerships to streamline customer management, test drives, vehicle stock, service requests, and automated order handling.

---

## 📦 Project Overview

This project simulates the CRM for an automobile company (WhatsNext Vision Motors), covering end-to-end vehicle lifecycle management including:

- Vehicle & Dealer Registration
- Customer Test Drive Scheduling
- Vehicle Order Management
- Stock Quantity Validation
- Scheduled Order Confirmations via Batch Jobs
- Automated Flows and Triggers for seamless processing

---

## 🧩 Objects & Relationships

| Object                    | Purpose                                | Relationships                     |
|--------------------------|----------------------------------------|-----------------------------------|
| `Vehicle__c`             | Stores vehicle details                 | Related to Dealer & Orders        |
| `Vehicle_Dealer__c`      | Stores authorized dealer info          | Related to Orders                 |
| `Vehicle_Customer__c`    | Stores customer details                | Related to Orders & Test Drives   |
| `Vehicle_Order__c`       | Tracks vehicle purchases               | Related to Customer & Vehicle     |
| `Vehicle_Test_Drive__c`  | Tracks test drive bookings             | Related to Customer & Vehicle     |
| `Vehicle_Service_Request__c` | Tracks service requests           | Related to Vehicle & Customer     |

---

## ⚙️ Key Features

### 🔹 Apex Classes
- `VehicleOrderTriggerHandler`: Validates stock and updates vehicle quantity when orders are placed.
- `VehicleOrderBatch`: Batch job that confirms pending orders if stock is available.
- `VehicleOrderBatchScheduler`: Schedules the batch job for regular execution.

### 🔹 Triggers
- `VehicleOrderTrigger`: Handles before/after insert/update logic using the handler class.

### 🔹 Automation
- **Flows**: (If any)
- **Validation Rules**: Ensure customer IDs, phone number formatting, and data quality.

---

## 🛠 Deployment Guide

1. Authorize your org:
   ```bash
   sf org login web --alias whatsnext
