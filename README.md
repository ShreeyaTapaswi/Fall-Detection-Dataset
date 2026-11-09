# Fall Detection Dataset for Elderly Safety

![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)
![Videos](https://img.shields.io/badge/Videos-59-blue)
![Format](https://img.shields.io/badge/Format-MP4-orange)

A video dataset for fall detection in surveillance-style footage, created by our team for the **Real-Time Fall Detection for Elderly Safety** project. The recordings are grouped by the person's starting posture (standing, sitting and sleeping), covering the situations in which falls happen to older adults.

---

## At a Glance

| | |
|---|---|
| **Total videos** | 59 |
| **Format** | `.mp4` |
| **Categories** | Standing (27), Sitting (17), Sleeping (15) |
| **Organization** | One folder per starting posture |
| **Annotation files** | Not included in this repository |
| **License** | [CC BY 4.0](LICENSE) |

---

## Repository Structure
Fall-Detection-Dataset/
├── Standing/ # 27 videos
├── Sitting/ # 17 videos
├── Sleeping/ # 15 videos
├── CITATION.cff
├── LICENSE
└── README.md

File names follow the pattern `video_YYYYMMDD_HHMMSS.mp4`, which is the date and time of the recording.

---

## Intended Use

- Training and evaluating fall detection models, especially pose-based pipelines
- Research on elderly safety and human activity recognition
- Teaching and demonstrations

This dataset was used to build a real-time pipeline that combines YOLOv11 pose estimation, a Transformer encoder over keypoint sequences and a physics-informed state machine. See the project repository: [Fall-Detection-For-Elderly](https://github.com/ShreeyaTapaswi/Fall-Detection-For-Elderly).

---

## Getting Started

```bash
git clone https://github.com/ShreeyaTapaswi/Fall-Detection-Dataset.git
```

Read the videos with OpenCV:

```python
import cv2
from pathlib import Path

for video_path in sorted(Path("Standing").glob("*.mp4")):
    cap = cv2.VideoCapture(str(video_path))
    fps = cap.get(cv2.CAP_PROP_FPS)
    frames = int(cap.get(cv2.CAP_PROP_FRAME_COUNT))
    print(video_path.name, f"{frames} frames @ {fps:.1f} FPS")
    cap.release()
```

---

## Limitations

- The dataset is small (59 clips), so it is best suited to prototyping, research and education rather than as a general benchmark.
- Videos are organized by starting posture. This repository does not include frame-level annotation files.

---

## Responsible Use

The recordings show people. We ask that the data be used for research and education on safety and activity recognition, and not to identify individuals or to monitor specific people.

---

## License

This dataset is released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license. You may share and adapt it, including for commercial purposes, as long as you give appropriate credit. See [LICENSE](LICENSE).

---

## How to Cite

If you use this dataset, please cite it. On GitHub you can also click **"Cite this repository"** in the right-hand sidebar.

**BibTeX**
```bibtex
@misc{tapaswi2026falldetectiondataset,
  author       = {Tapaswi, Shreeya and Lakare, Samruddhi and Karne, Vedant and Vidhate, Yash},
  title        = {Fall Detection Dataset for Elderly Safety},
  year         = {2026},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/ShreeyaTapaswi/Fall-Detection-Dataset}},
  note         = {Version 1.0.0}
}
```

**APA**
> Tapaswi, S., Lakare, S., Karne, V., & Vidhate, Y. (2026). *Fall Detection Dataset for Elderly Safety* (Version 1.0.0) [Data set]. GitHub. https://github.com/ShreeyaTapaswi/Fall-Detection-Dataset

---

## Authors

Shreeya Tapaswi, Samruddhi Lakare, Vedant Karne, Yash Vidhate
