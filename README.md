# ![Icon](favicon.png) Hamming Code (15,11) Visualizer

> **Do you wonder why your 1 TB hard drive doesn't actually use the full 1TB storage?**
>
> This is one of the many reasons: a section of memory is used for memory error correction. In this case, a 16-bit data block uses 5 bits to detect errors using Hamming Code parity checks.

## Overview
This project is an interactive visualization of the **Hamming Code (15,11)** error-correction algorithm. It demonstrates how parity bits are calculated and used to detect and correct single-bit errors in data transmission or storage.

## Features
- **Interactive Bit Grid**: Click any bit to flip its value (0/1) and simulate data corruption.
- **Real-time Parity Calculation**: Watch as parity bits update automatically based on the data bits.
- **Error Detection**: The system automatically detects if a single bit has been flipped and identifies the exact position of the error.
- **Scope Visualization**: Hover or click on parity rules to see exactly which bits are covered by each parity bit.
- **Visual Feedback**: Color-coded indicators for data bits, parity bits, and error states.

## How It Works
The simulation uses a **(15,11) Hamming Code** extended to 16 bits with an overall parity bit (SECDED - Single Error Correction, Double Error Detection).

1.  **Data Bits**: 11 bits are used for actual data.
2.  **Parity Bits**: 4 bits (at positions 1, 2, 4, 8) are used to store parity information.
3.  **Overall Parity**: Bit 0 checks the parity of the entire block.

### The Logic
- **Parity Check**: Each parity bit covers a specific set of bits. If the sum of 1s in that set is even, the parity is 0. If odd, it's 1.
- **Syndrome Calculation**: When checking for errors, the receiver calculates "syndrome" bits. If the syndrome is 0, there are no errors. If non-zero, the value of the syndrome points to the flipped bit.

## Usage
1.  Open `index.html` in your web browser.
2.  **Randomize Data**: Click the "Randomize Data" button to generate a new valid bit pattern.
3.  **Simulate Error**: Click any bit in the grid to flip it.
    - **Single Error**: The system will detect the error, highlight the corrupted bit in red, and show the "Syndrome" value.
    - **Double Error**: If you flip two bits, the system will detect a "Double Bit Error" (but cannot correct it).
4.  **Explore**: Click on the parity rules in the bottom panel to highlight the specific bits that each rule checks.

## Technologies
- **HTML5**
- **JavaScript (ES6)**
- **Tailwind CSS** (for styling)
- **Google Fonts** (JetBrains Mono)