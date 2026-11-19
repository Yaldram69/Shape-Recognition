# Shape Recognition

A webcam demo that runs a custom-trained YOLO model on live frames and displays the detections. The model file `best (9).pt` is a YOLO checkpoint produced during training; its class labels are not documented in this folder.

## Features

- Live detection from the default webcam using an Ultralytics YOLO model
- Uses the built-in Ultralytics `show=True` option for drawing results
- Press `q` to quit

## Project structure

- `ex.py` - webcam inference script
- `best (9).pt` - trained YOLO weights (custom model, about 6 MB)

## Requirements

Packages imported by `ex.py`:

- ultralytics (`YOLO`)
- opencv-python (`cv2`)

Install:

```bash
pip install ultralytics opencv-python
```

## Installation

```bash
pip install ultralytics opencv-python
```

## Usage

```bash
python ex.py
```

- Input: webcam (`cv2.VideoCapture(0)`)
- Output: Ultralytics display window (from `show=True`) and an OpenCV window titled "Webcam"
- Press `q` to quit

## Notes

- The model path in `ex.py` is `r"../best (9).pt"`, a path relative to the working directory, one level above the script's folder. If you run the script from this folder, the model will not be found. Either run it from a subfolder of this directory, or change the path to `"best (9).pt"`.
- The script draws the results twice: `show=True` opens the Ultralytics window and the frame is also shown with `cv2.imshow`. The OpenCV window shows the raw frame, not the annotated one, because the results are not plotted onto `frame`.
- The model's class names and training dataset are not included, so the classes it detects are unknown from this repository.
