# Mediapipe_TD

MediaPipe tracking (hand / face / pose) in TouchDesigner, running on an external Python 3.11 virtual environment managed with [TDPyEnvManager](https://github.com/oestricher/TDPyEnvManager).

## Contents

- `Mediapipe_TD.toe` — main TouchDesigner project
- `efficientdet_lite0.tflite` — EfficientDet-Lite0 object detection model
- `requirements.txt` — pinned dependencies of the Python vEnv
- `TDPyEnvManagerContext.*` — TDPyEnvManager configuration (vEnv mode, Python 3.11)

## Requirements

- TouchDesigner (2025.x) on Windows
- Python 3.11
- Webcam (for live tracking)

## Setup

1. Install Python 3.11.
2. Create the virtual environment next to the `.toe` and install dependencies:

   ```powershell
   py -3.11 -m venv MediaPipe_vEnv
   .\MediaPipe_vEnv\Scripts\python.exe -m pip install -r requirements.txt
   ```

3. Open `Mediapipe_TD.toe`. TDPyEnvManager picks up the `MediaPipe_vEnv` environment automatically (see `TDPyEnvManagerContext.yaml`).

## Notes

- `mediapipe==0.10.21` requires `numpy<2`, hence the `numpy==1.26.4` pin.
- `opencv-contrib-python` is required by MediaPipe; `opencv-python` is kept pinned to the same version to avoid binary conflicts.
