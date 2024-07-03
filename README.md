# Face Re-Identification with SCRFD and ArcFace

![Downloads](https://img.shields.io/github/downloads/yakhyo/face-reidentification/total)

<video controls autoplay loop src="https://github.com/yakhyo/face-reidentification/raw/main/assets/demo.mp4" muted="false"></video>
This repository implements face re-identification using SCRFD for face detection and ArcFace for face recognition. It supports inference from webcam or video sources.

## Features

- **Face Detection**: Utilizes [Sample and Computation Redistribution for Efficient Face Detection](https://arxiv.org/abs/2105.04714) (SCRFD) for efficient and accurate face detection.
- **Face Recognition**: Employs [ArcFace: Additive Angular Margin Loss for Deep Face Recognition](https://arxiv.org/abs/1801.07698) for robust face recognition.
- **Real-Time Inference**: Supports both webcam and video file input for real-time processing.

Project folder structure:

```
├── assets/
│   ├── demo.mp4
│   └── in_video.mp4
├── faces/
│   ├── face1.jpg
│   ├── face2.jpg
│   └── ...
├── models/
│   ├── __init__.py
│   ├── scrfd.py
│   └── arcface.py
├── utils/
│   └── helpers.py
├── main.py
├── README.md
└── requirements.txt
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yakyo/face-reidentification.git
cd face-reidentification
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

3. Download weight files:

```bash
sh download.sh
```

## Usage

```bash
python main.py --source assets/in_video.mp4
```

`main.py` arguments:

```
usage: main.py [-h] [--det-weight DET_WEIGHT] [--rec-weight REC_WEIGHT] [--similarity-thresh SIMILARITY_THRESH] [--confidence-thresh CONFIDENCE_THRESH]
               [--faces-dir FACES_DIR] [--source SOURCE] [--max-num MAX_NUM] [--log-level LOG_LEVEL]

Face Detection-and-Recognition

options:
  -h, --help            show this help message and exit
  --det-weight DET_WEIGHT
                        Path to detection model
  --rec-weight REC_WEIGHT
                        Path to recognition model
  --similarity-thresh SIMILARITY_THRESH
                        Similarity threshold between faces
  --confidence-thresh CONFIDENCE_THRESH
                        Confidence threshold for face detection
  --faces-dir FACES_DIR
                        Path to faces stored dir
  --source SOURCE       Video file or video camera source. i.e 0 - webcam
  --max-num MAX_NUM     Maximum number of face detections from a frame
  --log-level LOG_LEVEL
                        Logging level
```

## Reference

1. https://github.com/deepinsight/insightface/tree/master/detection/scrfd
2. https://github.com/deepinsight/insightface/tree/master/recognition/arcface_torch