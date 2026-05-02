# ⏳ Redstone Chronos: Decoding the Eternal Calendar

**A Minecraft Fabric Mod that translates complex chronological mathematics into visual Redstone logic.**

Redstone Chronos is an educational Minecraft mod built for Minecraft 1.20.1 (Fabric). It translates a complex, tabular perpetual calendar algorithm (originally designed by Arjun Prasad) into an interactive, in-game Redstone computer. By utilizing Modulo 7 arithmetic and Modulo 4 century shifts, this engine calculates the exact day of the week for any Gregorian date after October 1582.

---

## ✨ Features

* **The Java Math Engine:** A hardcoded backend that processes dates using modular arithmetic, century drift correction, and base-offset lookups.
* **NBT Structure Spawning:** Includes a custom item (`ChronosSpawnerItem`) that instantly generates a massive, pre-built Redstone "Hollywood Set" visualization (`chronos_machine.nbt`) into the world.
* **The Memory Matrix (ROM):** Translates standard numerical calendar offsets into specific Minecraft block variables (e.g., Diamond, Gold, Emerald).
* **Fabric 1.20.1 Optimized:** Built on the lightweight Fabric mod loader, perfectly compatible with performance mods like Sodium and Iris Shaders.

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
$\text{Final Day} = (\text{[Base Block Value]} + \text{[Century Shift]} + \text{[Leap Year Adjust]}) \pmod 7$

---

## 🛠️ Installation & Setup

### Prerequisites
* Java Development Kit (JDK) 17 or 21
* Minecraft Java Edition 1.20.1
* Fabric Mod Loader

### Building from Source
1. Clone the repository to your local machine:
   ```bash
   git clone [https://github.com/yourusername/redstone-chronos.git](https://github.com/yourusername/redstone-chronos.git)
