# Deal / No Deal – Browser Scoreboard

This is a simple browser-based scoreboard application designed to run locally and be projected on a screen while the game is played in person.

The program displays 10 cards, tracks rounds and remaining cases, plays audio effects, and shows banker interactions between rounds.

---

# How to Run

1. Download the project folder.
2. Open **index.html** in any modern browser (Chrome recommended).
3. When the program starts, you will be prompted to select a **folder (1–9)**.
4. The images inside that folder will be used as the game cards.

No installation or server is required.

---

# Folder Structure

The project requires the following folder structure:

```
project
│
├── index.html
├── script.js
├── style.css
│
└── assets
    │
    ├── card_back.png
    │
    ├── deal.png
    ├── no_deal.png
    ├── on_spacebar_press_banker.avif
    │
    ├── folders
    │   ├── 1
    │   │   ├── 10.jpeg
    │   │   ├── 20.jpeg
    │   │   ├── 30.jpeg
    │   │   ├── 50.jpeg
    │   │   ├── 60.jpeg
    │   │   ├── 75.jpeg
    │   │   ├── 100.jpeg
    │   │   ├── 150.jpeg
    │   │   ├── 200.jpeg
    │   │   └── 500.jpeg
    │   │
    │   ├── 2
    │   ├── 3
    │   ├── 4
    │   ├── 5
    │   ├── 6
    │   ├── 7
    │   ├── 8
    │   └── 9
    │
    └── sounds
        ├── welcome.mp3
        ├── deal_accept.mp3
        ├── no_deal.mp3
        ├── when_$10_card_flips.mp3
        ├── when_$500_card_flips.mp3
        ├── when_$20-$200_flips_1.mp3
        ├── when_$20-$200_flips_2.mp3
        ├── when_$20-$200_flips_3.mp3
        ├── when_$20-$200_flips_4.mp3
        ├── when_banker_comes.mp3
        ├── on_round_2_and_4.mp3
        ├── idle_1.mp3
        ├── idle_2.mp3
        ├── ...
        └── idle_14.mp3
```

---

# Changing the Card Images

Each game folder contains **10 images** representing the cards.

Example:

```
assets/folders/3/
```

Inside each folder you must include images with these filenames:

```
10.jpeg
20.jpeg
30.jpeg
50.jpeg
60.jpeg
75.jpeg
100.jpeg
150.jpeg
200.jpeg
500.jpeg
```

You can replace the images with any artwork you want, but **the filenames must stay the same**.

---

# Changing the Card Values

Card values are defined inside **script.js**.

Find this line near the top:

```javascript
const values = [10, 20, 30, 50, 60, 75, 100, 150, 200, 500];
```

You may change these numbers if desired.

Example:

```javascript
const values = [5, 10, 20, 25, 50, 100, 200, 500, 750, 1000];
```

If you change the values, you must also update the **image filenames** inside each folder to match.

Example:

```
1000.jpeg
```

---

# Changing Round Rules

Round settings are defined here:

```javascript
const roundConfig = { 
  1: 3,
  2: 2,
  3: 2,
  4: 1
};
```

Meaning:

Round 1 → open **3 cases**
Round 2 → open **2 cases**
Round 3 → open **2 cases**
Round 4 → open **1 case**

You can modify these numbers if desired.

---

# Game Controls

| Key            | Action                   |
| -------------- | ------------------------ |
| **Click Card** | Open a case              |
| **Spacebar**   | Advance banker / NO DEAL |
| **D**          | Accept DEAL              |
| **Z**          | Restart game             |

---

# Banker Behavior

When all cases for a round are opened:

1. Press **Spacebar**
2. The **Banker appears**
3. The player decides **Deal or No Deal**

Controls:

* **Spacebar → NO DEAL**
* **D → DEAL**

If DEAL is chosen, the game ends.

If NO DEAL is chosen, the next round begins.

---

# Audio Behavior

The program uses three types of audio:

### Background Music

Random idle tracks play during gameplay.

### Sound Effects

Card flips and decisions play unique sounds.

### Banker Audio

Different banker audio plays on:

* Round 2
* Round 4

This helps reduce repetition.

---

# Notes

• Do not rename files inside the **sounds** folder unless the script is updated.
• Card image filenames must match the values array.
• The game runs entirely in the browser and does not require internet access.

---

# Resetting the Game

Press:

```
Z
```

This reloads the page and resets the game.

---

# Browser Recommendation

For best performance:

**Google Chrome**
