# Desktop-Based Automated Coverage Map Screenshot System (Config-Driven, CSV Powered)

A configurable, desktop-based automation solution built using Power Automate Desktop (PAD) that captures coverage map screenshots for multiple addresses using a CSV-driven workflow.

This project demonstrates structured automation design, configuration-driven behavior, logging separation, and scalable processing architecture.

---

## Overview

This automation system:

- Reads multiple addresses from a CSV file
- Navigates to carrier coverage map pages
- Applies preset zoom strategies
- Captures map screenshots
- Saves images using dynamic naming conventions
- Maintains both client-level and developer-level logs

The system is fully configuration-driven via a JSON file, enabling easy scalability for additional carriers or presets.

---

## Architecture Highlights

- CSV-driven batch processing
- Subflow-based modular design
- Configuration-based carrier & zoom control
- Dynamic file naming strategy
- Structured logging (Client + Developer)
- Error handling with recovery logic
- Selector reliability strategy for stable UI automation

---

## How It Works

### 1️⃣ Input Processing
Addresses are loaded from:


/sample-data/addresses_sample.csv


Each address is processed using a `For Each` loop.

---

### 2️⃣ Configuration Driven Behavior

The system reads:


/sample-data/config_sample.json


Configuration controls:

- Carrier URL
- Default zoom preset
- Zoom direction (ZoomIn / ZoomOut)
- Zoom step count
- Output folder paths
- Log file paths

This design allows scaling without modifying core automation logic.

---

### 3️⃣ Screenshot Capture Logic

For each address:

- Navigate to coverage map URL
- Wait for required UI elements
- Apply zoom preset strategy
- Capture defined map area
- Save screenshot with dynamic filename

---

### 4️⃣ Dynamic File Naming Strategy

Screenshots are generated using:


[OutputFolder] + [DateFormat] + [CleanAddress] + [CarrierName] + .png


Example:


20260222_123_Main_St_Verizon.png


This ensures:

- No overwriting
- Clear traceability
- Organized storage

---

### 5️⃣ Logging Strategy

Two logging layers are maintained:

| Log Type | Purpose |
|----------|----------|
| client_summary.csv | High-level execution summary |
| developer_detailed.csv | Technical execution details & error diagnostics |

This separation simulates production-grade monitoring standards.

---

## Media Preview

All architecture screenshots are available inside the `/Media` folder:

- Flow Overview
- CSV Loop Processing
- Error Handling Logic
- Screenshot Capture Action
- File Naming Strategy
- Selector Mapping Strategy

Demo video available inside:


/Media/Coverage_System_Demo.mp4
> ![Coverage System Demo](./Media/Coverage_System_Demo.mp4)


---

## Engineering Considerations

- Modular subflow architecture
- Config-driven carrier scalability
- Stable UI selector strategy
- Explicit success/failure tracking
- Retry-aware error handling
- Structured variable naming
- Clean separation of responsibilities