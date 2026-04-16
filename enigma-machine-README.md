# Enigma Machine

A software simulation of the German WWII Enigma cipher machine, implemented in C. Accurately models the electromechanical substitution cipher including configurable rotors, a plugboard, and reflector.

---

## Background

The Enigma machine was used by Nazi Germany during WWII to encrypt military communications. Its complexity — with billions of possible configurations — made it one of the most sophisticated encryption systems of its era, until it was broken by Allied cryptanalysts including Alan Turing.

This project simulates the machine's encryption logic in software, faithfully reproducing its substitution and rotor-stepping behavior.

---

## Features

- **Configurable rotors** — Supports multiple rotor types with accurate wiring tables
- **Rotor stepping** — Implements the double-stepping anomaly found in real Enigma machines
- **Plugboard (Steckerbrett)** — Letter-swap pairs configurable before encryption
- **Reflector** — Ensures the machine is self-reciprocal (decryption = encryption)
- **Full encrypt/decrypt** — Any message encrypted with a given config can be decrypted with the same config

---

## How It Works

Each keypress passes a signal through:

1. **Plugboard** — Swaps letter pairs (optional, user-configured)
2. **Rotors (right → left)** — Each rotor applies a substitution cipher; rotors step forward on each keypress
3. **Reflector** — Sends the signal back through the rotors in reverse
4. **Rotors (left → right)** — Signal passes back through
5. **Plugboard again** — Final swap before output

This symmetric design means the same machine settings decrypt what they encrypt.

---

## Build & Run

```bash
git clone https://github.com/ad-fix/enigma-machine.git
cd enigma-machine
make
./enigma
```

---

## Example

```
Rotor Config : I II III
Ring Settings: A A A
Plugboard    : AZ BY CX

Input : HELLO
Output: MFNCU

# Using same settings:
Input : MFNCU
Output: HELLO
```

---

## Concepts Demonstrated

- Modular arithmetic and circular array indexing
- Bitwise logic and low-level data manipulation
- Struct-based modeling of hardware components in C
- Simulation of stateful, sequential systems

---

## Tech
**Language:** C  
**Environment:** Linux / Unix  
**Tools:** GCC, Make
