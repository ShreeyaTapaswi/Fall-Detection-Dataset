# Fall Detection Dataset for Elderly Safety

A custom video dataset for fall detection in surveillance-style footage, built by our team for the **Real-Time Fall Detection for Elderly Safety** project.

**Team:** Shreeya Tapaswi, Samruddhi Lakare, Vedant Karne, Yash Vidhate

Used by the project: [`ShreeyaTapaswi/Fall-Detection-For-Elderly`](https://github.com/ShreeyaTapaswi/Fall-Detection-For-Elderly)

---

## Overview

Falls are a major risk for older adults, and detecting them early matters. To train and test our fall detection pipeline, we collected our own video sequences instead of relying only on existing datasets.

The recordings are grouped by starting posture. Two of the fall situations our system handles are:

- **Standing-to-Fall**: a person who is walking or standing loses balance and falls. These falls show a fast drop of the body, high keypoint velocity and a loss of vertical orientation.
- **Sleeping-to-Fall** (bed/chair): a person falls from a bed or chair. These falls are subtler, with slower motion and different joint-angle patterns.

Keeping the cases separate lets each model learn the movement patterns specific to its posture.

---

## What's Inside

59 video recordings (`.mp4`), organized into folders by starting posture:

| Folder | Videos |
|---|---|
| `Standing/` | 27 |
| `Sitting/` | 17 |
| `Sleeping/` | 15 |

The data was used to train a pose-based pipeline: YOLOv11 pose estimation, followed by a Transformer encoder over sliding windows of keypoints, followed by a physics-informed state machine that confirms each fall.

---

## Use With the Project

This dataset powers the pipeline in the main project repository. See the project README for setup, the dashboard and how inference works:

[Fall-Detection-For-Elderly](https://github.com/ShreeyaTapaswi/Fall-Detection-For-Elderly)

---

## Citation

If you use this dataset, please credit the authors:
Tapaswi, S., Lakare, S., Karne, V., Vidhate, Y. Fall Detection Dataset for Elderly Safety. 2026.
https://github.com/ShreeyaTapaswi/Fall-Detection-Dataset
