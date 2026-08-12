# Experimental Results

## Overview

The proposed recognition approach was evaluated on both **single moving objects** and **multiple moving objects within the same video scene**.

Recognition is evaluated using **descriptive proximity**, a normalized similarity measure ranging from 0% to 100%.

A higher descriptive-proximity score indicates that the detected test object is more descriptively similar to a training object.

> **Note:** Descriptive proximity is a similarity measure produced by the proposed recognition framework. It should not be interpreted as conventional classification accuracy.

---

## Single Moving Object Recognition

The single-object experiments evaluate moving vehicles recorded under varied real-world conditions, including differences in:

- vehicle type
- recording location
- luminance
- viewpoint
- object orientation

Each detected test object was compared against the 18 training vehicle classes.

### Single-Object Descriptive Proximity Results

| Test Video ID | Descriptively Near Training Video ID | Descriptive Proximity |
|---:|---:|---:|
| 1 | 15 | 91.7% |
| 2 | 18 | 84.8% |
| 6 | 12 | 99.7% |
| 7 | 1 | 94.1% |
| 8 | 13 | 98.9% |
| 11 | 16 | 97.8% |
| 12 | 5 | 81.1% |
| 15 | 1 | 94.1% |
| 18 | 7 | 99.7% |
| 22 | 17 | 84.0% |
| 25 | 13 | 96.6% |
| 27 | 9 | 99.7% |

The reported single-object test cases produced nearest descriptive-proximity scores ranging from **81.1% to 99.7%**.

Several experiments also tested objects from viewpoints different from their corresponding training observations, including front, rear, and side views.

---

## Multiple Moving Object Recognition

The recognition framework was also evaluated on video sequences containing **two moving objects within the same scene**.

Each detected object was processed independently:

1. the foreground object was detected and segmented
2. its cell complex was constructed
3. its 4D shape-descriptor set was estimated
4. the descriptor was compared against the training dataset
5. descriptive proximity was calculated
6. the descriptively nearest training object was identified

### Multiple-Object Descriptive Proximity Results

| Test Video ID | Object | Descriptively Near Training Video ID | Descriptive Proximity |
|---:|---:|---:|---:|
| 31 | 1 | 1 | 98.4% |
| 31 | 2 | 1 | 91.4% |
| 32 | 1 | 1 | 90.8% |
| 32 | 2 | 15 | 90.9% |
| 33 | 1 | 7 | 98.8% |
| 33 | 2 | 11 | 97.6% |
| 34 | 1 | 1 | 92.0% |
| 34 | 2 | 7 | 99.9% |

Across these four multiple-object test videos, the eight independently detected objects produced nearest descriptive-proximity scores ranging from **90.8% to 99.9%**.

These experiments demonstrate that the descriptor-comparison process can be applied independently to multiple moving foreground objects detected within the same video sequence.

---

## Descriptive-Proximity Distribution

The thesis also summarizes the distribution of nearest descriptive-proximity scores across the broader test set.

| Descriptive Proximity Range | Number of Test Results |
|---|---:|
| 81–85% | 3 |
| 86–90% | 2 |
| 91–95% | 9 |
| 96–100% | 19 |

The distribution contains **33 reported test results**.

Most of the reported nearest descriptive-proximity values fall within the **91–100% range**.

Again, these percentages represent **descriptor-based similarity/nearness**, rather than conventional classification accuracy.

---

## Example: Multiple Moving Objects

Test Video 31 contains two independently detected moving vehicles.

The algorithm estimates the shape-descriptor set for each detected object and compares each one against the 18 training objects.

| Detected Object | Nearest Training Object | Descriptive Proximity |
|---|---:|---:|
| Object 1 | Vehicle 1 | 98.4% |
| Object 2 | Vehicle 1 | 91.4% |

[View Test Video 31 Demo](../assets/demos/vehicle-test31-detection.mp4)

![Test Video 31 Recognition Result](../assets/results/test31-recognition-result.png)

---

## Example: Viewpoint Variation

The experiments also evaluate recognition when a test vehicle is observed from a viewpoint different from the corresponding training observation.

This evaluates whether the temporal shape representation retains useful discriminative characteristics across changes in vehicle pose and viewing direction.

[View Viewpoint Test Demo](../assets/demos/vehicle-test36-detection.mp4)

![Viewpoint Recognition Result](../assets/results/test36-recognition-result.png)

---

## Interpretation

The experimental results demonstrate three important characteristics of the proposed approach:

### One Training Sample per Class

Each of the 18 vehicle classes is represented by one training video, demonstrating recognition under a limited-training-data setting.

### Viewpoint Variation

The test dataset includes vehicles observed from different orientations and under different environmental conditions.

### Multiple Object Processing

When multiple foreground objects are present, the algorithm estimates and compares a separate descriptor set for each detected object.

This extends the recognition framework from individual-object analysis to **multiple moving-object recognition within the same video scene**.

---

## Full Research Results

For the complete experimental analysis, figures, mathematical formulation, checkerboard visualizations, and discussion, refer to the full M.Sc. thesis:

**Temporal Multiple Moving Objects Recognition Using Shape-Based Descriptor Matching**

[View M.Sc. Thesis](https://mspace.lib.umanitoba.ca/items/a267fb22-720b-4493-96c1-e15bc2aefd8a)

