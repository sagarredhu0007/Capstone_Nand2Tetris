# Nand to Tetris I – Capstone Project: Make the Computer Draw a Box

**Course:** Nand to Tetris – I (ETCNTC301)  
**School:** School of Engineering & Technology, K.R. Mangalam University  
**Student Name:** Sagar  
**Roll Number:** 2501730360  
**Personal Parameter (K):** 60

---

## 📌 Project Overview

This repository contains the implementation of the Nand to Tetris I Capstone Project.

1. **Hack Computer Hardware (HDL):** `CPU.hdl`, `Memory.hdl`, and `Computer.hdl`.
2. **Two-Pass Hack Assembler (Python 3):** `assembler.py`, which assembles Hack Assembly programs and generates a symbol table (`symbols.txt`).
3. **Interactive Box Program:** `Box.asm`, assembled into `Box.hack`. The program polls the keyboard at `RAM[24576]` and draws a 16-pixel-wide, 20-row-tall black rectangle starting at Screen Row 60 while a key is pressed. The rectangle is erased when the key is released.
4. **Validation Tool:** `compare.py`, which compares assembled output against official benchmark files: Add, Max, Rect, and Pong.

## 📐 Personal Parameter Calculations (K = 60)

| Parameter | Formula | Value |
|---|---|---|
| Roll Number | 2501730360 | K = 60 (requested parameter) |
| Starting Screen Row | K | Row 60 |
| Ending Screen Row | K + 19 | Row 79 |
| Box Height | Fixed specification | 20 rows |
| Box Width | 16 × ((K mod 4) + 1) | 16 pixels |
| Words per Row | Width / 16 | 1 word |
| Starting Screen Address | 16384 + 32 × K | 18304 |
| Starting Address of Final Row | 16384 + 32 × 79 | 18912 |
| Extra Assembler Feature | K mod 3 | 0; the supplied implementation does not define an additional feature for this remainder. |

## 📁 Repository Structure

```text
Nand2Tetris_Capstone/
├── README.md
├── .gitignore
└── capstone/
    ├── assembler.py
    ├── Box.asm
    ├── Box.hack
    ├── compare.py
    ├── CPU.hdl
    ├── Memory.hdl
    ├── Computer.hdl
    ├── NOTES.md
    ├── visual_preview.html
    ├── run_assembler.bat
    ├── run_tests.bat
    └── tests/
        ├── Add.asm
        ├── Add.hack
        ├── Max.asm
        ├── Max.hack
        ├── Rect.asm
        ├── Rect.hack
        ├── Pong.asm
        └── Pong.hack
```

*Note: `symbols.txt` is generated locally by the assembler and is excluded from Git using `.gitignore`.*

## 🚀 How to Run and Test

### 1. Assemble Box.asm

```bash
cd capstone
python assembler.py Box.asm
```

This generates:
- `Box.hack` – assembled machine code (53 instructions).
- `symbols.txt` – generated symbol table.

### 2. Run Test Comparisons

```bash
python compare.py
```

The benchmark comparisons have produced the following results:

| Benchmark | Result |
|---|---|
| Add | PASSED |
| Max | PASSED |
| Rect | PASSED |
| Pong | PASSED (27,483 instructions) |

The comparisons verify that the generated machine code matches the corresponding official benchmark files.

### 3. Run the Box Program

**Option A – Interactive Browser Simulator**

Open `capstone/visual_preview.html` in Chrome or Edge. Hold down a key to display the box and release it to erase the box.

**Option B – Official CPU Emulator**

1. Open `CPUEmulator.bat` from your Nand2Tetris tools installation.
2. Load `capstone/Box.hack`.
3. Run the program.
4. Use the keyboard input to test the box drawing behavior.

## 🎓 Viva and Modification Guide

Refer to [`capstone/NOTES.md`](capstone/NOTES.md) for study notes and guidance on modifying the box position, width, height, and color.

---

**Project:** Nand to Tetris I Capstone  
**Student:** Sagar  
**Roll Number:** 2501730360  
**Personal Parameter:** K = 60