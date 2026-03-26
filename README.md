# Image-Based-Cancer-Diagnosis

Project focuses on diagnosing cancer through image analysis with a simple Streamlit frontend. It uses a pretrained `cnn_model.h5` and classifies histopathology images as `begin` or `malignant`.

## ⚙️ Requirements

- Python 3.10+ (for `Path | UploadedFile` union typing)
- `requirements.txt` includes:
  - `numpy`
  - `Pillow`
  - `tensorflow`
  - `streamlit`

## 🚀 Setup

1. Create and activate virtual environment:

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Ensure model + sample images exist:

- `cnn_model.h5` (pretrained tf.keras model)
- `sample_images/begin/*.jpg`
- `sample_images/malignant/*.jpg`

## ▶️ Run

```bash
streamlit run main.py
```

Open the link shown by Streamlit in your browser (typically `http://localhost:8501`).

## 🧠 Behavior

- Upload an image (`jpg`, `jpeg`, `png`) or pick a sample image.
- Model resizes upload to `224x224` using `tf.image.resize_with_pad`.
- Prediction is sigmoid output (`0..1`):
  - `< 0.5` → `begin`
  - `>= 0.5` → `malignant`

## 📁 Project files

- `main.py`: app logic (Streamlit UI, image loading, prediction)
- `cnn_model.h5`: pretrained model
- `sample_images/`: sample folders `begin`, `malignant`

## ⚠️ Disclaimer

This repository is for research/education only. It is not a validated clinical tool. Do not use in medical decision-making; consult specialists.


