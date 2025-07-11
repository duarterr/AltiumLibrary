
# Altium Component Library

  

A comprehensive PCB component library for Altium Designer, featuring standardized schematic symbols, footprints, and 3D models with consistent design rules and documentation.

  

## Library Standards

  

### Schematic Symbols

  

#### Pin Configuration

-  **Pin Length**: 100 mils (2.54mm)

-  **Pin Designation**: All pins must include proper electrical type designation:

-  **Input**: For signal inputs

-  **Output**: For signal outputs

-  **I/O**: For bidirectional pins

-  **Power**: For power supply pins (VDD, VCC, etc.)

-  **Passive**: For passive components (resistors, capacitors, etc.)

  
#### Symbol Requirements

- Clear pin numbering matching physical package

- Logical pin arrangement (power pins at top/bottom, I/O grouped by function)

- Proper pin names and designations

- Standard grid alignment (100 mils)

  

### Footprints

  

#### Layer Configuration

All footprints must include the following layers with specified line widths:

  

| Layer | Altium Layer | Purpose | Line Width |

|-------|--------------|---------|------------|

| **Top Overlay** | M13 | Component outline and reference designator | 0.152mm (6 mils) |

| **Bottom Overlay** | M14 | Bottom side component outline | 0.152mm (6 mils) |

| **Top Solder** | Yellow | Solder mask openings (top) | Auto-generated |

| **Bottom Solder** | Yellow | Solder mask openings (bottom) | Auto-generated |

| **Top Paste** | Gray | Solder paste stencil (top) | Auto-generated |

| **Bottom Paste** | Red | Solder paste stencil (bottom) | Auto-generated |

| **Multi-Layer** | Gray | Copper pads and vias | - |

| **Courtyard** | M15 | Component placement boundary | 0.05mm (2 mils) |

| **Assembly** | M3 | Assembly drawings and dimensions | 0.1mm (4 mils) |

| **3D Body** | M4 | 3D model body definition | 0.1mm (4 mils) |

  

#### Pad Specifications

-  **SMD Pads**: Must use rounded rectangles for improved soldering and reduced stress concentration

- **Pad Naming**: Sequential numbering starting from pin 1, following component datasheet

  

#### Courtyard Requirements

- **Clearance**: Minimum 0.25mm (10 mils) from component body outline

- **Line Width**: 0.05mm (2 mils)

- **Purpose**: Defines component placement boundary for DRC checking

- **Shape**: Rectangular boundary encompassing entire component including leads

  

#### Outline Requirements

- **Line Width**: 0.152mm (6 mils)

- **Layer**: Top Overlay (silkscreen)

- **Clearance**: Must not overlap with solder mask openings

- **Content**: Component body outline, pin 1 indicator, reference designator

  

### 3D Models

  

#### Model Requirements

- **Accuracy**: All 3D models must be dimensionally accurate to component datasheet specifications

- **Format**: STEP (.stp) or 3D Generic (.3dlib) format

- **Origin**: Model origin must align with footprint origin

- **Orientation**: Component must be oriented correctly for top-side placement

- **Detail Level**: Sufficient detail for accurate mechanical clearance checking

  

#### Model Sources

- Manufacturer-provided STEP models (preferred)

- Accurately dimensioned custom models

- Verified third-party models

  

### Component Documentation

  

#### Required Parameters

Each component must include the following parameters:

  

| Parameter | Description | Required |

|-----------|-------------|----------|

| **Description** | Clear component description | Yes |

| **Manufacturer** | Component manufacturer name | If applicable |

| **Part Number** | Manufacturer part number | If applicable |

| **Datasheet** | Direct link to manufacturer datasheet | Preferred |

| **Value** | Component value (for passives) | If applicable |
  

#### Documentation Best Practices

- Use manufacturer's official part numbers

- Include complete datasheet URLs (not shortened links)

- Provide clear, concise descriptions

- Include relevant electrical specifications

- Reference industry standard package names

  

## Library Organization

  

### Naming Convention
`[PREFIX]_[TECHNOLOGY]_[NAME]`

Examples:

- `RES_SMD_0603` (SMD resistor 0603 package)

- `CAP_PTH_D10x16mm` (Through-hole capacitor, 10mm diameter, 16mm height)

- `IC_SMD_SOIC8` (SMD integrated circuit, SOIC-8 package)

- `CONN_PTH_2x5_2.54mm` (Through-hole connector, 2x5 pins, 2.54mm pitch)

- `LED_SMD_3528` (SMD LED, 3528 package)

- `XTAL_SMD_3225` (SMD crystal, 3.2x2.5mm package)


  

## Quality Assurance

  

### Design Rule Checks

- All components must pass Altium's built-in DRC

- Courtyard clearance verification

- Electrical rule check (ERC) compliance

- 3D model collision detection

  

### Validation Process

1. **Symbol Verification**: Pin count, numbering, and electrical types

2. **Footprint Validation**: Dimensional accuracy against datasheet

3. **3D Model Check**: Mechanical fit and clearance verification

4. **Documentation Review**: Parameter completeness and accuracy

5. **Test Assembly**: Physical prototype validation when possible
