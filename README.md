# DES Straight P-Box Recovery

This repository contains a **Python-based cryptanalysis project** focused on recovering the
**straight permutation box (P-box)** used inside the DES round function.

The project is based on a **known-plaintext attack scenario**, where multiple plaintext–ciphertext
pairs and the encryption key are provided, but one internal DES component is missing.

---

## 🧠 Project Motivation

DES (Data Encryption Standard) relies on several fixed components:
- Initial and final permutations
- Expansion P-box
- S-boxes
- Straight P-box (permutation after S-boxes)

In this project, **all DES components are known except the straight P-box**.
The goal is to **reconstruct the unknown P-box** using:
- Known plaintext–ciphertext pairs
- The provided encryption key
- Structural properties of DES

---

## 🔍 Problem Setup

Given:
- 7 pairs of plaintext and ciphertext
- The correct DES key
- Known S-boxes and permutation boxes
- An **unknown straight P-box**

Objective:
- Recover the straight P-box table
- Use the recovered P-box to successfully decrypt the given ciphertexts

---

## 🛠️ Approach

The solution works by:
1. Analyzing DES round behavior before and after the straight P-box
2. Tracing bit dependencies through S-box outputs
3. Searching for valid permutations consistent with all known pairs
4. Using a **brute-force constrained search** to recover the P-box mapping

This approach leverages both:
- DES internal structure
- Consistency across multiple known plaintext–ciphertext pairs

---

## 📁 Repository Structure

├── main.py # Entry point for the recovery process
├── solve.py # Core logic for P-box reconstruction
├── findTable.py # Brute-force / constrained search for the P-box
├── boxes.py # DES S-boxes and known permutation tables
├── pad.py # Padding and helper utilities
├── pair.txt # Known plaintext–ciphertext pairs
├── output.txt # Intermediate recovered data (generated)
├── answer.txt # Final recovered P-box and decrypted result

---

## 📌 Results

- The straight P-box permutation is successfully recovered
- The recovered table is validated across all given input pairs
- Final decrypted output is provided in `answer.txt`

---

## 🎯 Learning Outcomes

This project demonstrates:
- Understanding of DES internal mechanics
- Practical cryptanalysis techniques
- Reverse engineering of cryptographic primitives
- Reasoning about bit-level transformations
- Python implementation of low-level crypto logic

---

## ⚠️ Disclaimer

This project is intended **strictly for educational purposes**.
