# Gravity Symbolic Discovery
![](images/Main.png)

> Can a neural-symbolic model rediscover the laws that a 3-year-old can intuitively grasp?

---

## 🧠 Why This Project?

This project was born from a single question:

> “If children can discover Newton's laws intuitively by age 3…  
> ...could a machine do the same, with no prior physics knowledge?”

Inspired by this thought, I built a system that uses **symbolic regression** to rediscover physical laws such as:

- $$( a = g )$$
- $$( a = \frac{2h}{t^2} )$$
- $$( F = ma )$$

The result?  
✅ It works — **three separate models**, each learning a core physical equation from data, with near-perfect accuracy.

---

## 📁 Project Structure


Each folder represents a self-contained model setup, trained on synthetic but physically realistic data.

---

## 🔬 Overview of Each Model

### 1️⃣ Clean Vacuum (`00_clean_vacuum`)

- No air resistance  
- Acceleration derived from time & height  
- Model discovers:
  $$a = g$$

---

### 2️⃣ Air & Water Resistance (`02_air_resistance`)

- Resistance factor alters fall time  
- Simulates air and water environments  
- Model discovers:
  $$a = g + R \cdot (R \cdot 0.2169 - 1.9325)$$
- A nonlinear correction for resistance — learned from scratch.

---

### 3️⃣ Newton’s Second Law (`03_force_equals_ma`)

- Inputs: mass and acceleration  
- Target: force  
- Model rediscovers:
  $$F = m \cdot a$$

✅ With perfect $$( R^2 = 1.0 )$$

---

## 🧠 Key Insight

> These models rediscover the same physical laws that humans learn through experience — but do so **only from data**, with no equations given.

Symbolic regression offers a powerful bridge between **machine learning** and **scientific reasoning**, generating interpretable formulas rather than black-box predictions.

---

## 📈 Tools Used

- `pysr` — Symbolic regression engine  
- `numpy`, `pandas` — Data simulation  
- `scikit-learn` — Evaluation metrics  
- `matplotlib` — Visualizations

Install all with:

```bash
pip install pysr numpy pandas scikit-learn matplotlib
