# Wardrobe
*Discover your confidence.*

Wardrobe is an iOS app that helps people decide, at a glance, whether a garment is likely to suit their body shape. The user takes or chooses one photo, and the app gives a clear verdict, a short reason, and a practical alternative.

All image analysis runs **on-device** with Apple's Foundation Models framework: no account, no server, and photos never leave the iPhone.

Built as a Challenge Based Learning project at the **Apple Developer Academy**.

---

## Features

- **Body-shape profile.** Enter bust, waist, hips and height; the app classifies the body shape as Pear, Hourglass, Apple or Inverted Triangle.
- **Does it fit?** Take a photo or pick one from the library.
- **On-device garment analysis.** Apple Intelligence describes the garment as structured data: category, cut, neckline and details.
- **Research-based verdict.** A styling lookup table turns that description into one of four results: *Suitable*, *Consider an alternative*, *No tip yet* or *No garment found*.
- **Explainable advice.** Every result says **what was detected**, **why it matters** for the user's shape, and **what to try instead**.
- **Privacy by design.** Fully offline analysis; photos are never uploaded.

---

## Architecture

The core idea: **the model sees, the table decides.** The on-device model only *describes* the garment; the advice comes from a deterministic, source-backed rule table. That makes results consistent and explainable.

~~~mermaid
flowchart LR
    A["📷 Photo<br/>Camera / Library"] --> B["GarmentAnalyzer<br/>Foundation Models"]
    B --> C["GarmentDescription<br/>@Generable struct"]
    C --> D["FashionRules<br/>Lookup table"]
    E["BodyShape<br/>from measurements"] --> D
    D --> F["FitVerdict"]
    F --> G["GarmentResult<br/>Results screen"]
~~~

---

## Requirements

- Xcode with the **iOS 27 SDK**
- iOS **27.0+**
- To use photo analysis on a physical device: an **Apple Intelligence–capable iPhone** with Apple Intelligence turned on and its model downloaded. Other screens work on any supported device.

---

## Getting Started

1. Clone the repository and open `1st-Challenge.xcodeproj` in Xcode.
2. Select the **1st-Challenge** target → **Signing & Capabilities** → choose your Team.
3. Run on a Simulator, or on a connected iPhone with Developer Mode enabled.
4. Enter your measurements, then tap **Does it fit?** and add a garment photo.

In debug builds, every analysis prints a `[GarmentAnalyzer]` line in Xcode's console showing exactly what the model returned.

---

## Sources

1. Look Good Feel Better: *Body Confidence Workbook* (2021)
2. CBSE Academic: *Dressing for Body Structure*
3. *Fashion, Style & Popular Culture*: [doi.org/10.1386/fspc_00117_1](https://doi.org/10.1386/fspc_00117_1)
4. Zong, W. (2022). *Dress Style Recommendation Based on Female Body Shapes*. M.A. thesis, Cornell University
5. *Construction for Fashion Design* (Bloomsbury)
6. [doi.org/10.1177/0887302X20905358](https://doi.org/10.1177/0887302X20905358)
7. [doi.org/10.1109/TMM.2020.2980195](https://doi.org/10.1109/TMM.2020.2980195)

---

## Team

Built at the **Apple Developer Academy** by:

- Fatimah Aljifry
- Atheer Alzhrani
- Joud Alassiri
- Hawraa Almuayrifi
- Deema Alqassem

Original repository: [Deemaaaal/1st-challenge-](https://github.com/Deemaaaal/1st-challenge-)



