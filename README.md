# REDSTONE CHRONOS: Decoding the Eternal Calendar

Translating Arjun Prasad's Algorithmic Calendar into Visual Logic Gates.

Adds an eternal calendar to your Minecraft world using advanced mathematical principles and Redstone logic.

---

## PANEL 1: Title & Core Concept

### The 7-Day Game Loop (Modulo Arithmetic)

Time operates on a strict 7-tick loop. In mathematics, this is called **Modulo 7 Arithmetic**. To find any day in the future or past, we don't need to count every single day; we only calculate the total days shifted and find the remainder when divided by 7.

**Mathematical Formula:**
```
Day ≡ X (mod 7)
```

This proves that the core of this project is grounded in real curriculum mathematics—modular arithmetic—a fundamental concept in number theory and computer science.

---

## PANEL 2: The Data Matrix (ROM)

### STEP 1: The Memory Matrix (Find your Base Code)

The Data Matrix acts as our Read-Only Memory (ROM). By cross-referencing the input Month/Date with the specific Year (00-99), the algorithm outputs an initial offset code. In our system, this offset is represented by a specific Minecraft Block value.

**How to Read the Matrix:**
- Locate your **Month** on one axis
- Locate your **Year** (00-99) on the other axis
- Cross-reference to find the **Base Block Value**

**Example Callout:** "Cross-referencing OCT 15 with YEAR 85 yields the [Diamond Block] offset."

This matrix is what translates the massive, intimidating chart from Arjun Prasad's original paper into a simple X/Y coordinate graph for finding a starting variable—making the complex algorithm accessible and implementable in Minecraft.

---

## PANEL 3: Century Correction (The Redstone Shift)

### STEP 2: Century Logic Gates (The Redstone Shift)

#### Fixing Server Lag (Gregorian Drift)

Because a solar year is slightly longer than 365 days, our calendar drifts. The Gregorian system fixes this by ignoring leap years on centuries unless they are divisible by 400. To calculate this 'drift' shift, we use Modulo 4 logic gates.

**The Math Formula:**
```
C_rem = (Century) mod 4
```

**The Output Rules (Minecraft Sign Format):**

| Remainder | Shift Output |
|-----------|--------------|
| 0         | +3 Days      |
| 1         | -3 Days      |
| 2         | -1 Day       |
| 3         | +1 Day       |

**Why This Matters:** This shows that we didn't just copy a chart—we understand the astronomical reason why the math works and how it corrects itself using remainders. The Gregorian calendar's leap year rules are encoded directly into our Redstone logic.

---

## PANEL 4: Final Decoding & The History

### STEP 3: Final Assembly & The Patch of 1582

**The Master Equation:**
```
Final Day = ([Base Block Value] + [Century Shift] + [Leap Year Adjust]) mod 7
```

**The Translation Key:**
```
0 = Sunday
1 = Monday
2 = Tuesday
3 = Wednesday
4 = Thursday
5 = Friday
6 = Saturday
```

### The 1582 Server Reset (Historical Fact)

This algorithm only calculates dates **AFTER October 1582**. Why?

Because Pope Gregory XIII implemented the "Gregorian Shift" to fix a massive calendar drift. To reset the system, **10 days were literally deleted from history**. October 4, 1582 was immediately followed by October 15, 1582. This deletion serves as our baseline zero for all calculations.

This is not just mathematical—it's historical. Your Eternal Calendar respects the actual calendar reform that changed the world.

---

## How It Works in Minecraft

1. **Input:** Select a month, day, and year using Minecraft blocks
2. **ROM Lookup:** Cross-reference the Data Matrix to get your base offset
3. **Century Calculation:** Apply Modulo 4 logic gates based on the century
4. **Leap Year Adjustment:** Account for the Gregorian leap year rules
5. **Final Calculation:** Apply Modulo 7 to get the day of the week
6. **Output:** The result displays which day your date falls on

---

## Mathematical Foundation

This project combines:
- **Modular Arithmetic** (Mod 7 for the weekly cycle)
- **Gregorian Calendar Rules** (Leap years, century adjustments)
- **Astronomical Principles** (The solar year drift and its correction)
- **Binary Logic Gates** (Redstone implementation)

---

## Technical Details

**Baseline:** October 15, 1582 (Gregorian Calendar adoption)  
**Calculation Scope:** October 1582 to any future date  
**Core Math:** Modulo 7 arithmetic with century and leap year corrections

---

## Credits

Algorithm based on Arjun Prasad's Algorithmic Calendar methodology.  
Implementation: Minecraft Redstone & Block Logic

---

## License

Add your license information here.