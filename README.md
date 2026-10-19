# Auto Detailing Inventory Management System

A lightweight, browser-based inventory and chemical consumption tracking tool designed for professional mobile detailing operations. The application automates per-order chemical deductions across multiple vehicle sizes, manages restocking thresholds, and dynamically generates reorder lists.

---

## Features

- **Automated Stock Deductions**: Deducts chemical and consumable usage based on service package recipes and vehicle size classifications.
- **Dynamic Threshold Alerts**: Categorizes stock health in real time:
  - **Full**: 100% capacity (unopened stock).
  - **Good**: > 50% capacity.
  - **Low**: ≤ 50% capacity.
  - **Warning**: ≤ 10% capacity (immediate restock required for upcoming jobs).
  - **None**: 0% capacity (out of stock).
- **Automated Shopping List**: Dynamically isolates materials flagged under Low, Warning, or None status for procurement planning.
- **Order Overdraft Protection**: Verifies available stock prior to order confirmation, preventing negative inventory states.

---

## Service Packages & Consumption Logic

Chemical and material deductions scale dynamically according to vehicle classification (`Small | Medium | Large`):

| Service Package | Water (gal) | R.Soap (oz) | P.Soap (oz) | Gloves (pcs) | Towels (pcs) | Glass Cln (oz) | Wax (oz) | Clay (bar) | Int Spray (oz) | P.Int Spray (oz) | Carpet Cln (oz) | Paint.C 1 (oz) | Paint.C 2 (oz) | H.Kit |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Basic Exterior** | 3 / 4 / 6 | 4 / 5 / 7 | — | 2 / 2 / 2 | 4 / 6 / 8 | 1 / 1 / 2 | — | — | — | — | — | — | — | — |
| **Premium Exterior** | 3 / 4 / 6 | — | 4 / 5 / 7 | 2 / 2 / 2 | 4 / 6 / 8 | 1 / 1 / 2 | 2 / 2 / 3 | 0.5 / 0.5 / 1 | — | — | — | — | — | — |
| **Basic Interior** | — | — | — | 2 / 2 / 2 | 6 / 8 / 10 | 1 / 1 / 2 | — | — | 2 / 2 / 3 | — | — | — | — | — |
| **Premium Interior** | 0.5 / 0.5 / 1 | — | — | 2 / 2 / 2 | 6 / 8 / 10 | 1 / 1 / 2 | — | — | — | 2 / 2 / 3 | 2 / 2 / 4 | — | — | — |
| **Basic Detail** | 3 / 4 / 6 | 4 / 5 / 7 | — | 2 / 2 / 2 | 10 / 14 / 18 | 1 / 1 / 2 | — | — | 2 / 2 / 3 | — | — | — | — | — |
| **Premium Detail** | 3.5 / 4.5 / 7 | — | 4 / 5 / 7 | 2 / 2 / 2 | 10 / 14 / 18 | 1 / 1 / 2 | 2 / 2 / 3 | 0.5 / 0.5 / 1 | — | 2 / 2 / 3 | 2 / 2 / 4 | — | — | — |
| **Standard Paint Correction** | 2 / 3 / 4 | — | — | 2 / 2 / 2 | — | — | 2 / 2 / 3 | 0.5 / 0.5 / 1 | — | — | — | 3 / 5 / 8 | — | — |
| **2-Step Paint Correction** | 2 / 3 / 4 | — | — | 2 / 2 / 2 | — | — | 2 / 2 / 3 | 0.5 / 0.5 / 1 | — | — | — | 3 / 5 / 8 | 3 / 5 / 8 | — |
| **Headlight Restoration** | — | — | — | — | — | — | — | — | — | — | — | — | — | 1 / 1 / 1 |

---

## Base Pack Sizes

Capacity baselines are calculated per unopened unit container:

- **Water**: 100 gallons/unit
- **R.Soap**: 32 oz/bottle
- **P.Soap**: 32 oz/bottle
- **Gloves**: 100 gloves/box
- **Towels**: 200 towels/pack
- **Wax Spray**: 16 oz/bottle
- **Clay Bar**: 6 bars/box
- **Int. Spray**: 18 oz/bottle
- **PInt.Spray**: 16 oz/bottle
- **Glass Cleaner**: 32 oz/bottle
- **Carpet Cleaner**: 32 oz/bottle
- **1Paint.C (Step 1 Compound)**: 36 oz/bottle
- **2Paint.C (Step 2 Polish)**: 36 oz/bottle
- **H.Kit (Headlight Restoration)**: 3 kits/box

---

## Installation & Usage

### Running Locally
1. Clone the repository:
   ```bash
   git clone [https://github.com/KameronChambers/detailing_inventory.git](https://github.com/KameronChambers/detailing_inventory.git)
   cd detailing_inventory
