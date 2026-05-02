# ⏳ Redstone Chronos: Eternal Calendar

![Minecraft Version](https://img.shields.io/badge/Minecraft-1.21.1-2b4a11?style=for-the-badge&logo=minecraft)
![Mod Loader](https://img.shields.io/badge/Fabric-0.116.11-D2C6A3?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.0.0-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**A Minecraft Fabric Mod that translates complex Class 12 chronological mathematics into interactive visual Redstone logic.**

Built as a specialized mathematics exhibition project, Redstone Chronos translates a tabular perpetual calendar algorithm (originally conceptualized by Arjun Prasad) into a working, in-game computation engine. By utilizing **Modulo 7 arithmetic** and **Modulo 4 century shifts**, this mod calculates the exact day of the week for any Gregorian date after the historical 1582 server patch.

---

## ✨ Features

* **The Java Math Engine:** A hardcoded backend that processes dates using modular arithmetic, century drift correction, and base-offset matrix lookups.
* **NBT Structure Spawning:** Includes a custom item that instantly generates a massive, pre-built Redstone "Hollywood Set" visualization (`chronos_machine.nbt`) into the world to visually demonstrate the data flow.
* **The Memory Matrix (ROM):** Translates standard numerical calendar offsets into specific Minecraft block variables (e.g., Diamond, Gold, Emerald).
* **Fabric 1.21.1 Optimized:** Built natively for modern Minecraft, ensuring compatibility with top-tier optimization mods like Sodium and Iris Shaders.

---

## 🧮 The Mathematics (How it Works)

The mod breaks down the Gregorian calendar into three logical computational steps:

### 1. The 7-Day Game Loop (Modulo 7)
Time operates on a strict 7-tick loop. To find any day in history, we don't count every day; we calculate the total days shifted and find the remainder when divided by 7. 

### 2. The Data Matrix (ROM Lookup)
The algorithm cross-references the input Month and specific Year (00-99) to output an initial offset code. In the mod, this variable is represented by a specific Minecraft Block value.

### 3. Century Logic Gates (The Redstone Shift)
To fix "server lag" (Gregorian calendar drift), the system drops leap years on centuries unless divisible by 400. This is calculated using Modulo 4 logic gates:
* $C_{rem} = (\text{Century}) \pmod 4$
* Remaining values determine a shift of +3, -3, -1, or +1 days.

**The Final Master Equation:**
> $\text{Final Day} = (\text{[Base Block Value]} + \text{[Century Shift]} + \text{[Leap Year Adjust]}) \pmod 7$

---

## 📥 Installation

This repository includes the compiled ready-to-play `.jar` files for standard users, as well as the source code for developers.

### For Players & Judges (Standard Install)
1. Ensure you have **Minecraft Java Edition 1.21.1** installed.
2. Install the [Fabric Loader](https://fabricmc.net/) for 1.21.1.
3. Download the following files from this repository:
   * `eternal-calendar-1.0.0.jar`
   * `fabric-api-0.116.11+1.21.1.jar` (Required dependency)
4. Drop both `.jar` files into your Minecraft `%appdata%/.minecraft/mods` folder.
5. Launch the game using the Fabric profile!

### For Developers (Viewing the Code)
If you want to view the raw Java mathematics and implementation:
* Download `eternal-calendar-1.0.0-sources.jar` and extract it to view the uncompiled `.java` backend.

---

## 🎮 Usage In-Game

1. Boot up a Minecraft world with the mod active.
2. Open the Creative Inventory and navigate to the **Redstone** tab.
3. Equip the custom **Chronos Spawner** item.
4. Right-click any block on the ground.
5. The mod will execute the NBT spawner, instantly pasting the visual Redstone calculator matrix directly in front of you.

---

## 📜 Credits & License

* **Core Java Architecture & Implementation:** Pratyush Kumar (Class 12 Exhibition Project)
* **Original Mathematical Algorithm:** Arjun Prasad 
* **Platform:** FabricMC Ecosystem
* **License:** See the `LICENSE` file in this repository for usage rights.
