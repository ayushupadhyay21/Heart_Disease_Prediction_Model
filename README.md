# ❤️ Heart Disease Prediction

Predict the risk of heart disease with a simple, interactive **Streamlit** app powered by a **K-Nearest Neighbors (KNN)** model.

<p align="center">
  <img alt="Heart_Disease_Prediction_Model" src="assets/screenshot.png" width="720"/>
</p>

<p align="center">
  <a href="#-quick-start"><img alt="Made with Python" src="https://img.shields.io/badge/Python-3.13%2B-blue"/></a>
  <a href="#-run-locally"><img alt="Streamlit" src="https://img.shields.io/badge/Streamlit-App-red"/></a>
  <a href="#-model-card"><img alt="Model" src="https://img.shields.io/badge/Model-KNN-success"/></a>
  <a href="#-license"><img alt="License" src="https://img.shields.io/badge/License-MIT-green"/></a>
</p>

---

## 🔗 What is this?

A compact ML project that:

* Performs **EDA & preprocessing** in a notebook (`HeartdiseaseFinal.ipynb`).
* Trains and persists a **KNN classifier** (`KNN_heart.pkl`).
* Applies **feature scaling** (`scaler.pkl`) and a fixed **column order** (`columns.pkl`).
* Serves predictions via a **Streamlit** app (`app.py`).
* Uses the classic **heart disease dataset** (`heart.csv`).

---

## 📦 Project Structure

```
.
├── app.py                       # Streamlit web app
├── heart.csv                    # Dataset
├── HeartdiseaseFinal.ipynb      # EDA, preprocessing, training
├── KNN_heart.pkl                # Trained KNN model
├── scaler.pkl                   # Standard/MinMax scaler for inputs
├── columns.pkl                  # Expected input columns order
├── requirements.txt             # (Optional) pinned dependencies
└── assets/
    └── screenshot.png           # App screenshot (add your image)
```

---

## ⚡ Quick Start

### 1) Clone & enter the project

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2) Create a virtual environment (recommended)

```bash
# Windows
python -m venv .venv && .venv\Scripts\activate

# macOS / Linux
python3 -m venv .venv && source .venv/bin/activate
```

### 3) Install dependencies

```bash
pip install -r requirements.txt
# or, if you don't have a requirements file
pip install streamlit pandas scikit-learn joblib
```

### 4) Run locally

```bash
streamlit run app.py
```

Then open the URL shown in your terminal (usually [http://localhost:8501](http://localhost:8501)).

---

## 🧪 Example Input Features

These columns are expected by the app/model (see `columns.pkl` for the exact order):

* `Age`, `Sex`, `ChestPainType`, `RestingBP`, `Cholesterol`, `FastingBS`, `RestingECG`, `MaxHR`, `ExerciseAngina`, `Oldpeak`, `ST_Slope`, `HeartDisease` (target)

> The app handles encoding + scaling using the saved `columns.pkl` and `scaler.pkl` artifacts.

---

## 🧠 Model Card

* **Algorithm:** K-Nearest Neighbors (KNN)
* **Training:** See `HeartdiseaseFinal.ipynb` for EDA, preprocessing, and training code.
* **Artifacts:**

  * `KNN_heart.pkl` — Trained classifier
  * `scaler.pkl` — Feature scaler used at train time
  * `columns.pkl` — List of feature names and order expected by the model
* **Intended Use:** Educational/demo app to illustrate classification and basic MLOps practices (artifacts + app).
* **Limitations:** Not a medical device. Predictions may be biased by dataset artifacts; do **not** use for clinical decisions.

---

## 🧰 Retraining / Modifying the Model

1. Open `HeartdiseaseFinal.ipynb` and run all cells to reproduce preprocessing and training.
2. Export updated artifacts (`KNN_heart.pkl`, `scaler.pkl`, `columns.pkl`).
3. Ensure `app.py` loads the new artifacts and matches feature order.
4. Re-run the app: `streamlit run app.py`.

---

## 🖥️ Run as a Script (Optional)

If you expose a CLI in `app.py`, you might support something like:

```bash
python app.py --predict --age 54 --sex M --restingbp 130 --chol 240 --maxhr 150 ...
```

(Adjust to your implementation.)

---

## ☁️ Deploy (Optional)

* **Streamlit Community Cloud:** Push your repo to GitHub and deploy via Streamlit Cloud UI.
* **Docker:**

  ```dockerfile
  FROM python:3.13-slim
  WORKDIR /app
  COPY . .
  RUN pip install -r requirements.txt
  EXPOSE 8501
  CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
  ```

---

## 🔄 Git & GitHub Quick Guide

From your project folder, run:

```bash
git init
git add .
git commit -m "Initial commit: heart disease prediction app"

git branch -M main
# Replace with your repo URL
git remote add origin https://github.com/<your-username>/<your-repo-name>.git

git push -u origin main
```

> If your default branch is `master`, replace `main` accordingly.

---

## 🧩 Troubleshooting

* **Module not found:** Ensure your virtual environment is activated and dependencies are installed.
* **Shape/column errors:** Delete stale artifacts and re-export `columns.pkl` to match your preprocessing.
* **Streamlit not launching:** Try `python -m streamlit run app.py` to avoid PATH issues.

---

## 🤝 Contributing

1. Fork the repo
2. Create a feature branch: `git checkout -b feat/my-change`
3. Commit: `git commit -m "feat: describe change"`
4. Push: `git push origin feat/my-change`
5. Open a Pull Request

---

## 📜 License

Released under the **MIT License**. See `LICENSE` for details.

---

## 👤 Author

**Ayush Upadhyay**
GitHub: [@ayushupadhyay21](https://github.com/ayushupadhyay21)

> *This project is for educational purposes only and should **not** be used for medical diagnosis or treatment.*
