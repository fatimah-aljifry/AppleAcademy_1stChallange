# Wardrobe 
*Discover your confidence.*

Wardrobe is an iOS app that helps people decide, at a glance, whether a garment is likely to suit their body shape. The user takes or chooses one photo, and the app gives a clear verdict, a short reason, and a practical alternative.

All image analysis runs **on-device** with Apple's Foundation Models framework: no account, no server, and photos never leave the iPhone.

Built as a Challenge Based Learning project at the **Apple Developer Academy**.

---

##  Features

- **Body-shape profile.** Enter bust, waist, hips and height; the app classifies the body shape as Pear, Hourglass, Apple or Inverted Triangle.
- **Does it fit?** Take a photo or pick one from the library.
- **On-device garment analysis.** Apple Intelligence describes the garment as structured data: category, cut, neckline and details.
- **Research-based verdict.** A styling lookup table turns that description into one of four results: *Suitable*, *Consider an alternative*, *No tip yet* or *No garment found*.
- **Explainable advice.** Every result says **what was detected**, **why it matters** for the user's shape, and **what to try instead**.
- **Privacy by design.** Fully offline analysis; photos are never uploaded.

---

##  Architecture

The core idea: **the model sees, the table decides.** The on-device model only *describes* the garment; the advice comes from a deterministic, source-backed rule table. That makes results consistent and explainable.

```mermaid
flowchart LR
    A[📷 Photo<br/>Camera / Library] --> B[GarmentAnalyzer<br/>Foundation Models]
    B --> C[GarmentDescription<br/>@Generable struct]
    C --> D[FashionRules<br/>Lookup table]
    E[BodyShape<br/>from measurements] --> D
    D --> F[FitVerdict]
    F --> G[GarmentResult<br/>Results screen]
