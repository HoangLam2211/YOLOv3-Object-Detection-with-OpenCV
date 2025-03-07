# YOLOv3 Object Detection

This project implements object detection using the YOLOv3 model with OpenCV. It allows inference on images, videos, and real-time webcam streams.

## Features
- **Supports multiple input sources**: images, videos, and webcam
- **Adjustable confidence and threshold settings** for better detection control
- **Outputs processed videos** with detected objects
- **Displays real-time detections** for webcam streams
- **Downloads YOLOv3 weights** if not available locally

## Installation

### 1. Clone the repository
```bash
git clone [https://github.com/your-repo/yolov3-object-detection.git](https://github.com/HoangLam2211/YOLOv3-Object-Detection-with-OpenCV/edit/main/README.md)
cd yolov3-object-detection
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```
Ensure you have OpenCV installed:
```bash
pip install opencv-python numpy
```

### 3. Download YOLOv3 Model (Optional)
If you don't have the YOLOv3 weights and configuration files, you can download them by running:
```bash
./yolov3-coco/get_model.sh
```

Alternatively, manually download the following files and place them in the `yolov3-coco/` directory:
- `yolov3.weights`: [Download Here](https://pjreddie.com/media/files/yolov3.weights)
- `yolov3.cfg`: [Download Here](https://github.com/pjreddie/darknet/blob/master/cfg/yolov3.cfg)
- `coco.names`: [Download Here](https://github.com/pjreddie/darknet/blob/master/data/coco.names)

## Usage

### 1. Run object detection on an image
```bash
python detect.py --image-path path/to/image.jpg
```

### 2. Run object detection on a video
```bash
python detect.py --video-path path/to/video.mp4
```

### 3. Run real-time object detection using webcam
```bash
python detect.py
```

## Command-line Arguments
| Argument | Description |
|----------|-------------|
| `-m, --model-path` | Path to the directory with YOLOv3 model files |
| `-w, --weights` | Path to the YOLOv3 weights file |
| `-cfg, --config` | Path to the YOLOv3 config file |
| `-l, --labels` | Path to the COCO labels file |
| `-i, --image-path` | Path to an image for detection |
| `-v, --video-path` | Path to a video for detection |
| `-vo, --video-output-path` | Path to save the output video |
| `-c, --confidence` | Confidence threshold (default: 0.5) |
| `-th, --threshold` | Non-Max Suppression threshold (default: 0.3) |
| `-t, --show-time` | Display inference time |

## Output
- **Image**: The processed image with detected objects will be displayed.
- **Video**: The processed video will be saved to `output.avi` (default).
- **Webcam**: A window will display real-time detections (press `q` to exit).

## Troubleshooting
- Ensure the model files (`.weights`, `.cfg`, `coco.names`) are correctly placed.
- Verify OpenCV and NumPy are installed.
- For slow webcam performance, reduce frame processing frequency in the script.

## License
This project is open-source under the MIT License.

## Acknowledgments
- [YOLO: Real-Time Object Detection](https://pjreddie.com/darknet/yolo/)
- OpenCV for computer vision functions

