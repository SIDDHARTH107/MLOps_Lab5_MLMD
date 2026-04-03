# Real-Time Payment Failover Monitoring using Apache Beam (MLOps Lab 5)

## Project Overview

Modern payment systems must handle failures in real time. When a payment gateway goes down, companies must automatically reroute traffic to another gateway or choose a backup gateway to prevent revenue loss and poor customer experience.

This project simulates a **Real-Time Payment Failover Monitoring System** using:

* Apache Beam (Streaming Pipeline)
* Python
* Windowed Analytics
* Failover Simulation
* Logging & Metrics
* Interactive Visualization using Plotly 

The system generates streaming payment data, detects gateway failures, calculates failure rates, automatically simulates failover, logs events, and visualizes performance.

This lab tries mimics how real-world payment infrastructure works in companies like:

* Stripe
* PayPal
* Banking and fintech payment systems

---

# Problem Statement

In real-world payment systems:

* Payments are processed through multiple gateways
* Sometimes gateways fail
* Failure spikes must be detected quickly
* Traffic must be rerouted automatically
* Engineers must monitor logs and metrics

This project solves:

**How to detect payment failures in real-time and automatically simulate failover using Apache Beam streaming pipelines.**

---

# Architecture

```
Streaming Payment Generator
            ↓
     Apache Beam Pipeline
            ↓
     Failure Detection
            ↓
     Windowed Failure Rate
            ↓
     Automatic Failover
            ↓
      Logging & Metrics
            ↓
 Interactive Visualization
```

---

# Features

## Real-Time Payment Streaming

* Simulated payment generator
* Multiple gateways:

  * Stripe
  * PayPal
  * Bank API
* Random success / failure generation

---

## Window-Based Failure Monitoring

* 1-minute window
* Detect failure spikes
* Real-time gateway monitoring

---

## Automatic Failover Simulation

When failure rate crosses threshold:

* Gateway marked as unstable
* Payments rerouted automatically
* Backup gateway selected instantly

---

## Interactive Visualization

Using Plotly:

* Gateway failure rate charts
* Interactive viz. (bar chart)
* Hover-based analytics

---

# Project Structure

```
MLOps_Lab5_MLMD/
│
├── Real_Time_Payment_Failover.ipynb
│
├── requirements.txt
│
└── README.md
```

---

# Tech Stack

### Programming

* Python

### Data Processing

* Apache Beam

### Visualization

* Plotly
* Matplotlib (Optional)

---

# Installation

Clone Repository

```
git clone https://github.com/SIDDHARTH107/MLOps_Lab5_MLMD.git
```

Navigate to Project

```
cd MLOps_Lab5_MLMD
```

Install Requirements

```
pip install -r requirements.txt
```

---

# Requirements

requirements.txt

```
apache-beam
plotly
matplotlib
pandas
numpy
```
---

# Pipeline Workflow

## Step 1 — Generate Streaming Payments

Simulates:

* Payment ID
* Gateway
* Status
* Timestamp

Example Output:

```
Payment ID: 1023
Gateway: Stripe
Status: Failed
```

---

## Step 2 — Detect Failures

Pipeline identifies failed payments:

```
Payment Failure Detected
```

---

## Step 3 — Windowed Failure Rate

1-minute window:

```
Stripe → Failure Rate: 0.31
PayPal → Failure Rate: 0.12
```

---

## Step 4 — Automatic Failover

When threshold exceeded:

```
⚠️ FAILOVER ALERT: Switch from Stripe
🔄 Routing payment 3456 from Stripe → PayPal
```

Example:

```
PaymentID=2345 Gateway=Stripe Status=Failed
```

---

## Step 6 — Visualization

Interactive Plotly Dashboard:

* Gateway failure rate
* Real-time monitoring
* Hover analytics

---

# Example Output

Console Output

```
Stripe → Failure Rate: 0.32
⚠️ FAILOVER ALERT: Switch from Stripe

🔄 Routing payment 2345 from Stripe → PayPal
```

---

# Real-World Applications

This architecture is used in:

* Payment Gateways
* Banking Systems
* Fintech Infrastructure
* Fraud Detection Systems
* Transaction Monitoring Systems

---

# Author

Siddharth Mohapatra | Northeastern University | M.S. Data Analytics Engineering

---
