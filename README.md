# 📊 Azure Project 2: Cost Monitoring & Tagging

## 👨‍💻 Goal  
Track resource costs, apply tags for better visibility, and set up budget alerts to monitor and control Azure spending.

---

## 🧠 Topics Covered

- Azure Cost Management
- Resource Tagging Strategy
- Budget Alerts
- Subscription-Level Cost Analysis
- Filtered Cost Breakdown by Tags

---

## 📘 Summary

This project focuses on managing and visualizing Azure resource costs by using **tags**, **budgets**, and the **Cost Analysis dashboard**. You'll create tagged resources, track spending by tags, and set up a budget alert for proactive cost management.

---

## 📌 Scenario

You are running multiple projects in Azure and need to track usage costs by environment and project. Tags provide the ability to filter and group costs effectively, and budget alerts help you avoid unexpected charges.

---

## 🛠️ Steps Implemented

### 1. Create a Tagged Resource

1. Go to **Azure Portal** → **Resource groups** → **Create**  
   - Name: `az900-project2-rg`  
   - Region: `East US`  
   - Click **Review + create** → **Create**

2. Go to **Storage accounts** → **Create**
   - **Resource group**: `az900-project2-rg`
   - **Storage account name**: `az900costsa` *(must be globally unique)*
   - **Performance**: Standard  
   - **Redundancy**: Locally-redundant storage (LRS)  
   - Click **Next: Tags**

3. Under **Tags**, add:
   - `Environment` → `Dev`
   - `Project` → `AZ900`
   - Click **Next** or **Review + create** → **Create**

---

### 2. Enable Cost Analysis

1. Go to **Cost Management + Billing** → **Cost analysis**
2. Set the following filters:
   - **Scope**: Your Subscription
   - **Time Range**: *Month to date*
   - **Group by**: *Service name*
3. You’ll see visual cost breakdown by services used (e.g., Storage, Compute).

---

### 3. Create a Budget Alert

1. Go to **Cost Management + Billing** → **Budgets** → **+ Add**
2. Fill in the form:
   - **Scope**: Your subscription
   - **Name**: `AZ900-Zero-Spend-Budget`
   - **Reset period**: Monthly
   - **Budget amount**: `$0.01` *(minimum value)*
   - **Alert conditions**: Actual > 0
   - **Alert recipient(s)**: Your email address
3. Click **Create**

✅ You'll now be notified if any cost is incurred.

---

### 4. View Costs by Tag

1. In **Cost analysis**, click **+ Add filter**
2. Select:
   - **Tag** → `Project`
   - **Value** → `AZ900`
3. View the chart to monitor costs for all resources tagged with `Project = AZ900`

This allows granular cost tracking by project, environment, or department.

---

## 🚨 Cleanup

To delete all resources and avoid charges:

1. Go to **Resource groups**
2. Select `az900-project2-rg`
3. Click **Delete resource group**

---

## ✅ Outcome

- Resources tagged for project-level cost tracking
- Budget alert set to notify on zero-spend threshold
- Able to filter and group cost data by tags in Azure Cost Analysis
- Project supports cost governance best practices in a real-world Azure setup

---
