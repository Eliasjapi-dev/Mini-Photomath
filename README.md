# Mini Photomath

## Description

**English:** Mini Photomath is a real-time handwritten math solver. Using OpenCV and a TensorFlow Lite CNN, it detects digits and symbols from a webcam feed, reconstructs the arithmetic expression, and displays the result instantly.

**Español:** Mini Photomath es un solucionador de operaciones matemáticas escritas a mano en tiempo real. Con OpenCV y una CNN en TensorFlow Lite, detecta dígitos y símbolos desde la cámara web, reconstruye la expresión aritmética y muestra el resultado al instante.

## Features / Funcionalidades

- Real-time ROI selection with adjustable sliders for global and individual regions
- Handwritten digit and symbol detection (0–9, +, -, ×, ÷, brackets, dot)
- Expression parsing and evaluation
- TFLite model for lightweight inference
- Dataset preprocessing and training scripts

## Requirements / Requisitos

- Python 3.8+
- OpenCV
- TensorFlow & TensorFlow Lite
- NumPy
- json

## Installation / Instalación

```bash
# Clone the repository
git clone https://github.com/youruser/mini-photomath.git
cd mini-photomath

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/macOS
.
venv\Scripts\activate   # Windows

# Install dependencies
pip install -r requirements.txt
```

## Dataset & Preprocessing / Dataset y Preprocesamiento

- Place your symbol dataset in `dataset_symbols/`
- MNIST digits are loaded automatically via TensorFlow
- Run the preprocessing script:
  ```bash
  python preprocess.py
  ```

## Training / Entrenamiento

```bash
python train.py --epochs 30 --batch-size 64
```

Outputs:

- `model_cnn.keras` (full Keras model)
- `model_cnn.tflite` (TensorFlow Lite)

## Convert to TFLite / Conversión a TFLite

If you already have a `.keras` model:

```bash
python convert_to_tflite.py --input model_cnn.keras --output model_cnn.tflite
```

## Usage / Uso

```bash
python main.py --model model_cnn.tflite
```

- Adjust ROI sliders in the separate control windows
- View detected ROIs, parsed expression, and result in the main window

## Configuration / Configuración

- **ROI Global:** X, Y, Width, Height sliders
- **ROIs Individuales:** Min/Max Width, Min/Max Height, Min/Max Area sliders

## Contributing / Contribuyendo

PRs welcome! Please fork the repo and create a feature branch.

## License

This project is licensed under the MIT License. / Este proyecto está bajo la licencia MIT.

