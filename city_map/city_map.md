# City Map Problem

## Problem Overview

The Trisolarans have built a thriving civilization across their chaotic three-star system. They manage a gigantic city, which can be represented as an **n-row by m-column rectangle**. The city has a center located at row **x₀**, column **y₀**. Each cell in the city is represented by a character, and the city map is drawn according to specific rules.

## Map Drawing Rules

### 1. Center and Lines
- Place a **plus sign (+)** at the city center
- Draw a **horizontal line of minus signs (-)** through the center row (excluding the center cell)
- Draw a **vertical line of vertical bars (|)** through the center column (excluding the center cell)
- Draw **four diagonal lines** from the city center:
  - Top-left with **\\**
  - Top-right with **/**
  - Bottom-right with **\\**
  - Bottom-left with **/**
  - Each diagonal extends until the map boundary

### 2. Region Labeling
The above lines divide the city into **eight regions**. Fill each region with a letter from **A to H** in **clockwise order**, as shown below:

```
         |
    G  \ | /  A
        \|/
   ------+------
        /|\
    F  / | \  C
         |
         
Clockwise: H(top) → A → B(right) → C → D(bottom) → E → F(left) → G → H
```

Visual representation:
```
┌────────────────────┐
│       H     A      │
│   G  \ | /    B    │
│       \|/          │
│  ------+------     │
│       /|\          │
│   F  / | \    C    │
│       E     D      │
└────────────────────┘
```

## Example

For **n = 8**, **m = 16** and center at **(4, 8)**, the city map looks like:

```
GGGG\HH|AA/BBBBB
GGGGG\H|A/BBBBBB
GGGGGG\|/BBBBBBB
-------+--------
FFFFFF/|\CCCCCCC
FFFFF/E|D\CCCCCC
FFFF/EE|DD\CCCCC
FFF/EEE|DDD\CCCC
```

## Your Task

The city is so large that Trisolarans must rely on GPS for navigation. They hope you can help develop a **Toolle Map app**:

**Given a GPS location (row x, column y), draw a 5×5 city map centered at (x, y).**

### Input
- City dimensions: **n** rows, **m** columns
- City center: row **x₀**, column **y₀**
- Query location: row **x**, column **y**

### Output
- A **5×5 grid** showing the city map centered at position (x, y)
- If the window extends beyond city boundaries, handle appropriately

## Special Cases to Consider

1. **Center cell of the entire city**: Always displays **'+'**
2. **Center row cells** (not at center): Display **'-'**
3. **Center column cells** (not at center): Display **'|'**
4. **Diagonal cells**: Display **'\\'** or **'/'**
5. **Window boundary**: The 5×5 window might extend beyond the map edges
6. **Small maps**: When n or m < 5
7. **Query near edges**: When (x, y) is close to map boundaries
8. **Query at or near city center**: Special handling for center markers

## Constraints
- Rows and columns are typically 0-indexed or 1-indexed (clarify based on problem source)
- The 5×5 window is centered at the query position
- Need to handle out-of-bounds cells appropriately