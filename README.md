# Open Robotics Nomenclature Standard (r1.2026)

We define a standardized nomenclature conventions for the classification, identification, and interoperability specification of robotic systems. This standard enables universal communication of robotic capabilities, form factors, and technical specifications across manufacturers, deployment environments, and regulatory frameworks.

**Version:** 1.0 (2026)  
**Status:** Draft Proposal  
**License:** MIT

---

## 1. Purpose and Scope

### 1.1 Objectives
This standard provides:
- A unified naming convention for all robotic platforms
- Machine-readable specifications for automated compatibility assessment
- Human-readable designations for procurement, regulation, and deployment
- Framework for modular component interoperability
- Foundation for safety certification and insurance frameworks

### 1.2 Scope
This standard applies to:
- Autonomous and semi-autonomous robotic systems
- Humanoid, animal-form, and specialized robotic platforms
- Industrial, commercial, consumer, and research applications
- Ground-based, aerial, aquatic, and hybrid locomotion systems

---

## 2. Nomenclature Structure

### 2.1 General Format
```
[MANUFACTURER]-[FORM]-[SIZE]-[SPECIFICATIONS]-[CONNECTIVITY]
```

### 2.2 Component Definitions

Each designation consists of the following mandatory and optional fields:

| Field | Type | Description | Example |
|-------|------|-------------|---------|
| MANUFACTURER | Mandatory | Organization or brand identifier | TESLA, BOSTON, XPENG |
| FORM | Mandatory | Physical form factor and configuration | NAHT2RM, FW2R, BAQ |
| SIZE | Mandatory | Physical scale classification | XS, M, XL, MECH |
| SPECIFICATIONS | Mandatory | Performance and capability metrics | 10B200P62D |
| CONNECTIVITY | Mandatory | Communication protocols | 5GSAT, 6WMX |

### 2.3 Complete Example
```
WARMACH-NAHT2RM-XL-10B200P62D-5GSAT
```

**Translation:**  
War Machine manufacturer, Neutral humanoid on hexapod tread base with 2 arms and masculine proportions, Extra-Large size (300-500cm), 10-hour battery, 200kg payload, 62 degrees of freedom, 5G and satellite connectivity.

---

## 3. Form Factor Codes (FORM)

### 3.1 Parsing Rules
Form codes are read left-to-right with the following priority:
1. **Animal indicators** (A + letter): AQ, AV, AS, AH, AO, AF
2. **Numeric modifiers** (number + letter): 1R, 2R, 3R, etc.
3. **Single-character codes**: M, F, N, C, B, W, T
4. **Scale keywords**: NANO, MICRO

### 3.2 Humanoid Form Factors

| Code | Description | Application |
|------|-------------|-------------|
| **M** | Masculine proportions | Industrial, security, general purpose |
| **F** | Feminine proportions | Service, hospitality, healthcare |
| **N** | Neutral/androgynous | Universal applications, research |
| **C** | Cylindrical torso | Space-efficient, industrial |
| **B** | Box-frame | Utilitarian, minimal aesthetic |

### 3.3 Animal-Inspired Forms

| Code | Description | Locomotion | Typical Use Cases |
|------|-------------|------------|-------------------|
| **AQ** | Quadruped | Four legs | Inspection, patrol, rough terrain |
| **AV** | Avian | Wings/flight | Aerial surveillance, delivery |
| **AS** | Serpentine | Snake-like | Confined spaces, pipes, search & rescue |
| **AH** | Hexapod | Six legs | Extreme terrain, stability |
| **AO** | Octapod | Eight legs | Heavy loads, redundancy |
| **AF** | Aquatic | Fins/propellers | Underwater inspection, marine research |

### 3.4 Locomotion Base

| Code | Description | Terrain Suitability |
|------|-------------|---------------------|
| **W** | Wheeled base | Smooth surfaces, indoor |
| **T** | Tracked/tread base | Mixed terrain, outdoor |
| **2T** | Dual Tracked/tread bases | Mixed terrain, outdoor |
| **nT** | n Tracked/tread bases | Mixed terrain, space, outdoor |

### 3.5 Manipulation Appendages

| Code | Description | Typical DOF Range |
|------|-------------|-------------------|
| **1R** | Single arm | 6-12 DOF |
| **2R** | Two arms | 12-40+ DOF |
| **3R** | Three arms | 18-60+ DOF |
| **4R** | Four arms | 24-80+ DOF |
| **nR** | n arms | Variable |

### 3.6 Scale Modifiers

| Code | Description | Typical Dimensions |
|------|-------------|-------------------|
| **NANO** | Nanoscale | <1mm (experimental/medical) |
| **MICRO** | Microscale | 1mm-3cm |

### 3.7 Form Code Examples

| Complete Code | Interpretation |
|---------------|----------------|
| **NAHT2RM** | Neutral humanoid, hexapod base, tracked locomotion, 2 arms, masculine |
| **FW2R** | Feminine humanoid, wheeled base, 2 arms |
| **BAQ** | Box-frame quadruped |
| **CASW** | Cylindrical aquatic serpentine, wheeled (hybrid) |
| **MICROAV** | Microscale avian (flying micro-drone) |

---

## 4. Size Classification (SIZE)

Size determines physical footprint, workspace requirements, and safety considerations.

| Code | Height/Length Range | Typical Applications |
|------|---------------------|----------------------|
| **XS** | <30 cm | Inspection crawlers, micro-drones, tabletop assistants |
| **S** | 30-100 cm | Companion robots, small quadrupeds, desktop manipulators |
| **M** | 100-200 cm | Human-scale humanoids, service robots, standard industrial |
| **L** | 200-300 cm | Large humanoids, heavy-duty quadrupeds, warehouse automation |
| **XL** | 300-500 cm | Industrial giants, construction robots, heavy manipulation |
| **MECH** | >500 cm | Megascale platforms, mining, construction, disaster response |

**Note:** For non-humanoid forms, size refers to maximum dimension (length, wingspan, etc.)

---

## 5. Technical Specifications (SPECIFICATIONS)

Specifications are concatenated without delimiters and parsed using numeric prefixes.

### 5.1 Battery/Runtime (B)

| Format | Description | Example |
|--------|-------------|---------|
| **nB** | n hours of battery operation | 8B = 8 hours |
| **nL** | n liters of fuel (gasoline/diesel) | 5L = 5 liters |
| **nLnH** | n liters fuel, n hours runtime | 5L10H = 5L for 10hrs |
| **nLnB** | n liters fuel + n hours battery (hybrid) | 5L10B = 5L fuel + 10hr battery |
| **X** | Tethered power (unlimited) | X = external power |
| **SOL** | Solar powered | SOL = solar only |
| **SOLnH** | Solar, n hours runtime | SOL5H = solar, 5hr |
| **SOLnB** | Solar + n hours battery | SOL10B = solar + 10hr battery |
| **SOLnHnB** | Solar n hours + battery n hours | SOL5H10B = solar 5hr + battery 10hr |

### 5.2 Payload Capacity (P/T)

| Format | Description | Example |
|--------|-------------|---------|
| **nP** | n kilograms payload | 50P = 50kg |
| **nT** | n metric tonnes payload | 2T = 2 tonnes (2000kg) |

**Note:** Payload is maximum safe working load including tools, carried objects, and consumables.

### 5.3 Degrees of Freedom (D)

| Format | Description | Example |
|--------|-------------|---------|
| **nD** | n total degrees of freedom | 62D = 62 DOF |

DOF indicates total articulation points across all joints and appendages.

**Reference Ranges:**
- **<20D:** Basic manipulation, limited dexterity
- **20-40D:** Moderate dexterity, general industrial tasks
- **40-60D:** High dexterity, complex assembly
- **60D+:** Near-human dexterity, fine motor tasks

---

## 6. Connectivity (CONNECTIVITY)

Connectivity codes indicate communication protocols and network capabilities.

| Code | Description | Typical Use Case |
|------|-------------|------------------|
| **6W** | WiFi 6 (802.11ax) | Indoor, high bandwidth |
| **7W** | WiFi 7 (802.11be) | Ultra-high bandwidth, low latency |
| **5G** | 5G cellular | Outdoor, mobile operations |
| **LTE** | 4G LTE cellular | Wide coverage, moderate bandwidth |
| **MX** | Mesh networking | Swarm coordination, redundancy |
| **SAT** | Satellite communications | Remote operations, global coverage |
| **BT** | Bluetooth | Short-range, accessories |
| **LORA** | LoRaWAN | Long-range, low power |
| **ZIGBEE** | Zigbee mesh | IoT integration, smart facilities |

**Note:** Multiple connectivity modes are concatenated: **5GSAT** = 5G + Satellite

---

## 7. Complete Designation Examples

### 7.1 Industrial Warehouse Robot
```
AMAZON-NW2R-M-8B50P35D-6WMX
```
- Amazon manufacturer
- Neutral humanoid, wheeled, 2 arms
- Medium size (100-200cm)
- 8-hour battery, 50kg payload, 35 DOF
- WiFi 6 + mesh networking

### 7.2 Military Disaster Response
```
WARMACH-NAHT2RM-XL-10B200P62D-5GSAT
```
- War Machine manufacturer
- Neutral hexapod tracked, 2 arms, masculine
- Extra-large (300-500cm)
- 10-hour battery, 200kg payload, 62 DOF
- 5G + satellite

### 7.3 Consumer Home Assistant
```
XPENG-FT2R-M-6B15P42D-6W
```
- XPENG manufacturer
- Feminine humanoid, tracked base, 2 arms
- Medium size (100-200cm)
- 6-hour battery, 15kg payload, 42 DOF
- WiFi 6

### 7.4 Agricultural Platform
```
JOHNDEERE-NAQ2R-MECH-X50P18D-5G
```
- John Deere manufacturer
- Neutral quadruped, 2 arms
- Mech scale (>500cm)
- Tethered power, 50kg payload, 18 DOF
- 5G connectivity

### 7.5 Underwater Inspection
```
NAVY-CAF1R-S-SOL5H10B20P28D-SAT
```
- Navy manufacturer
- Cylindrical aquatic form, 1 arm
- Small (30-100cm)
- Solar 5hr + battery 10hr, 20kg payload, 28 DOF
- Satellite (surface communication)

---

## 8. Parsing Algorithm

### 8.1 Specification Field Parsing
The SPECIFICATIONS field is parsed using the following algorithm:

```
1. Scan left-to-right
2. When digit encountered:
   a. Consume all consecutive digits (n)
   b. Consume next letter(s) until next digit or end
   c. Interpret as metric: nX where X is unit code
3. Special cases:
   - SOL: Check for following digits
   - X alone: Tethered power
4. Return array of (value, unit) pairs
```

**Example:** `10B200P62D`
```
→ 10 + B = 10-hour battery
→ 200 + P = 200kg payload  
→ 62 + D = 62 degrees of freedom
```

### 8.2 Form Field Parsing
The FORM field is parsed using the following priority:

```
1. Check for scale keywords (NANO, MICRO) - consume if found
2. Scan for 'A' + letter combinations (AQ, AV, etc.) - consume if found
3. Scan for digit + 'R' combinations (1R, 2R, etc.) - consume if found
4. Remaining single letters parsed as individual modifiers (M, F, N, W, T, etc.)
```

**Example:** `NAHT2RM`
```
→ N = Neutral
→ AH = Hexapod
→ T = Tracked
→ 2R = 2 arms
→ M = Masculine
```

---

## 9. Extension Framework

### 9.1 Optional Modifier Codes
Implementations MAY extend designations with optional suffixes:

| Code | Description | Example |
|------|-------------|---------|
| **-A0** to **-A4** | Armor/protection rating (0=none, 4=combat) | -A3 |
| **-V** | Vision only | -V |
| **-VL** | Vision + LiDAR | -VL |
| **-VLR** | Vision + LiDAR + Radar | -VLR |
| **-VLRT** | Vision + LiDAR + Radar + Thermal | -VLRT |
| **-EMP** | EMP hardened | -EMP |
| **-CAMO** | Adaptive camouflage | -CAMO |
| **-BIO** | Biohazard rated | -BIO |
| **-EX** | Explosion-proof | -EX |

**Example with extensions:**
```
MILITARY-NAHT2RM-XL-10B200P62D-5GSAT-A4-VLR-EMP
```

### 9.2 AI Stack Designation (Optional)
```
[BASE-DESIGNATION]-AI:[MODEL]
```

**Examples:**
- `XPENG-FT2R-M-6B15P42D-6W-AI:GPT5`
- `BOSTON-NAQ2R-L-8B50P40D-6WMX-AI:CLAUDE4`

---

## 10. Interoperability Standards

### 10.1 Component Interface Codes
For modular systems, components may be designated separately:

#### 10.1.1 Manipulation Modules
```
[TYPE]-[FINGERS]-[FORCE]-[INTERFACE]
```

**Examples:**
- `GRIPPER-2F-100N-STD-A` (2-finger, 100N grip, standard interface A)
- `HAND-5F-50N-STD-A` (5-finger, 50N/finger, standard interface A)
- `SUCTION-4CUP-500N-STD-B` (4 suction cups, different mounting)

#### 10.1.2 Sensor Modules
```
[TYPE]-[SPEC]-[INTERFACE]
```

**Examples:**
- `VISION-RGBD-120FOV-STD-E` (RGB-D camera, 120° FOV)
- `LIDAR-360-100M-STD-F` (360° LiDAR, 100m range)
- `TACTILE-ARRAY-STD-G` (Tactile sensor array)

#### 10.1.3 Locomotion Modules
```
[TYPE]-[VARIANT]-[INTERFACE]
```

**Examples:**
- `LEG-HUMANOID-STD-C`
- `LEG-DIGITIGRADE-STD-C` (bird-like)
- `WHEEL-OMNI-STD-D`
- `TRACK-HEAVY-STD-C`

### 10.2 Interface Standards
Standard interfaces (STD-A, STD-B, etc.) define:
- Mechanical mounting specifications
- Electrical power delivery
- Data communication protocols
- Safety interlock mechanisms

---

## 11. Compliance and Certification

### 11.1 Compliance Levels

| Level | Description | Requirements |
|-------|-------------|--------------|
| **ORNS-BASIC** | Basic nomenclature compliance | Follows naming convention only |
| **ORNS-VERIFIED** | Verified specifications | Third-party tested specifications |
| **ORNS-CERTIFIED** | Full certification | Safety tested, interoperability verified |
| **ORNS-MODULAR** | Modular interoperability | Component-level compatibility |

### 11.2 Certification Authority
Certification should be administered by an independent International Robotics Standards Organization (IRSO) with:
- Industry consortium representation
- Academic participation
- Government safety agency oversight
- Insurance industry input

---

## 12. Usage Guidelines

### 12.1 Procurement Specifications
Organizations may specify requirements using wildcards:

```
Request: 100 units matching: *-2R-M-8B+50P+35D+-6W-
```

This requests:
- Any manufacturer
- 2 arms, medium size
- Minimum 8hr battery, 50kg payload, 35 DOF
- Must have WiFi 6

### 12.2 Safety Zoning
Facilities may restrict robot classes:

```
Zone A: M-size only, max 50P payload
Zone B: M or L-size, max 100P payload  
Zone C: Any size, any payload (restricted access)
```

### 12.3 Insurance Classification
Insurance premiums may be calculated based on:
- Size classification (larger = higher premiums)
- Payload capacity (higher = greater risk)
- DOF complexity (more = higher risk)
- Armor/protection level (higher = more dangerous applications)

---

## 13. Governance and Evolution

### 13.1 Version Control
- Major versions (n.YYYY): Breaking changes to parsing or structure
- Minor revisions (n.m.YYYY): Additive changes, new codes
- Current version: **r1.2026**

### 13.2 Amendment Process
1. Proposal submission to IRSO standards committee
2. Public comment period (90 days)
3. Committee review and refinement
4. Industry voting (requires 2/3 majority)
5. Publication and implementation timeline

### 13.3 Backwards Compatibility
New versions must maintain backwards compatibility for designations created under previous versions. Deprecated codes must be supported for minimum 10 years after deprecation.

---

## 14. Reference Implementation

A reference parser implementation is available at:
```
https://github.com/open-robotics/orns-parser
```

Implementations are available in:
- Python
- JavaScript/TypeScript
- Rust
- C++
- Go

---

## Appendix A: Quick Reference Chart

| Category | Codes | Examples |
|----------|-------|----------|
| **Humanoid Forms** | M, F, N, C, B | M, FT2R, NW2R |
| **Animal Forms** | AQ, AV, AS, AH, AO, AF | AQ, AHAS, AO2R |
| **Locomotion** | W, T | W, T, WT (hybrid) |
| **Arms** | 1R, 2R, 3R, 4R... | 2R, 4R |
| **Scale** | NANO, MICRO, XS, S, M, L, XL, MECH | M, XL, MECH |
| **Power** | nB, nL, SOL, X | 10B, 5L10B, SOL5H10B |
| **Payload** | nP, nT | 50P, 2T |
| **DOF** | nD | 35D, 62D |
| **Connectivity** | 6W, 7W, 5G, MX, SAT, BT, LORA | 6WMX, 5GSAT |

---

## Appendix B: Complete Example Gallery

```
TESLA-MT2R-L-12B30P22D-6W5G                    // Tesla Optimus Gen 3
BOSTON-NAQ-M-4B14P12D-6WMX                     // Boston Dynamics Spot  
XPENG-FT2R-L-6B15P62D-6W5G                     // XPENG IRON
UNITREE-N-M-4B5P23D-6W                         // Unitree G1 Basic
FIGURE-NT2R-L-8B50P40D-6WMX                    // Figure AI Figure 03
1X-FT2R-M-4B20P35D-6W-AI:CUSTOM                // 1X NEO
AGILITY-N-L-8B35P28D-6WMX                      // Agility Digit
WARMACH-NAHT2RM-XL-10B200P62D-5GSAT-A4-EMP     // Military combat platform
AMAZON-NW2R-M-8B50P35D-6WMX                    // Amazon warehouse picker
NAVY-CAF1R-S-SOL5H10B20P28D-SAT                // Naval underwater drone
```

---

**End of Open Robotics Nomenclature Standard (r1.2026)**
