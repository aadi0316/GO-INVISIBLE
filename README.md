# 🧥 GO INVISIBLE 

A real-time **Harry Potter-style invisibility cloak** effect built with Python and OpenCV. Any object of a specific color (default: green/teal) becomes transparent, revealing a pre-captured background in its place.

---

## 🎥 How It Works

1. **Background capture** — A still frame is captured at startup (before you enter the frame). This becomes the "background" that shines through the cloak.
2. **HSV masking** — Each live frame is converted to HSV color space. A color range mask isolates the cloak pixels.
3. **Frame blending** — The cloak region is replaced with the corresponding pixels from the background frame, while the rest of the live frame is kept intact.
4. **Interactive tuning** — Six trackbars let you fine-tune the HSV range in real time to match your specific cloak color.

```
Live Frame  ──►  HSV Mask  ──►  Cloak region  ──►  Replaced with background
                               Non-cloak region ──►  Kept from live frame
                                                         │
                                                         ▼
                                                    Final Output
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- A webcam

### Installation

```bash
git clone https://github.com/your-username/invisibility-cloak.git
cd invisibility-cloak
pip install opencv-python numpy
```

### Run

```bash
python cloak.py
```

> **Tip:** When the script starts, **step out of frame** for ~1 second while it captures the background. Then step back in wearing your cloak!

Press **`q`** to quit.

---

## 🎛️ Trackbar Controls

An interactive window called **"bars"** lets you tune the HSV color range on the fly:

| Trackbar | Range | Default | Description |
|---|---|---|---|
| `lower_hue` | 0 – 180 | 68 | Lower bound of hue |
| `lower_saturation` | 0 – 255 | 55 | Lower bound of saturation |
| `lower_value` | 0 – 255 | 54 | Lower bound of brightness |
| `upper_hue` | 0 – 180 | 110 | Upper bound of hue |
| `upper_saturation` | 0 – 255 | 255 | Upper bound of saturation |
| `upper_value` | 0 – 255 | 255 | Upper bound of brightness |

The defaults are tuned for **green/teal** fabric. Adjust to match your cloak's color.

---

## 🎨 Choosing Your Cloak Color

For best results, use a **solid, brightly colored** fabric that contrasts with your environment. Some common color ranges in HSV:

| Color | Lower HSV | Upper HSV |
|---|---|---|
| Green / Teal *(default)* | `[68, 55, 54]` | `[110, 255, 255]` |
| Red | `[0, 120, 70]` | `[10, 255, 255]` |
| Blue | `[100, 150, 50]` | `[130, 255, 255]` |

---

## 📁 Project Structure

```
invisibility-cloak/
│
├── cloak.py        # Main script
└── README.md
```

---

## ⚠️ Known Limitations

- The background must remain **static** after startup — any movement or lighting change will degrade the effect.
- Performance depends on your machine and webcam resolution.
- Lighting conditions significantly affect HSV accuracy; tune the trackbars for your environment.

---

## 🛠️ Built With

- [OpenCV](https://opencv.org/) — Computer vision and image processing
- [NumPy](https://numpy.org/) — Array operations and kernel creation

---
