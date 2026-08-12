# Temporal Single & Multiple Moving Object Recognition

**One-shot recognition of single and multiple moving objects in complex video using temporal 4D shape descriptors and descriptive proximity.**

This repository presents my M.Sc. research in Computer Vision at the **Computational Intelligence Laboratory, University of Manitoba**.

The research investigates how **single and multiple moving objects** can be recognized from video using **shape-based temporal representations rather than requiring large labeled image datasets**. The proposed approach estimates **four-dimensional (4D) shape descriptors** for moving objects and compares those descriptors using descriptive proximity to identify objects with similar characteristics.

[View M.Sc. Thesis](https://mspace.lib.umanitoba.ca/items/a267fb22-720b-4493-96c1-e15bc2aefd8a)

---

## Research Problem

Recognizing moving objects in real-world video is challenging because object appearance can change due to:

* viewpoint
* movement
* scale
* background complexity
* partial visual variation across frames
* the presence of multiple moving objects within the same scene

Many recognition approaches depend on large training datasets containing multiple examples of each object class.

This research explores a different approach: **recognizing both single and multiple moving objects using only a single training example per class** by characterizing their shape and temporal behavior through four-dimensional descriptors.

The **one-shot setting** refers to the availability of only one training example for each object class, while the recognition framework is evaluated on both individual moving objects and scenes containing multiple moving objects.

---

## Proposed Approach

The method extends shape-based object representation into the **temporal domain**.

At a high level, the recognition pipeline is:

```text
Input Video
    ↓
Moving Object Detection / Extraction
    ↓
Single or Multiple Object Representation
    ↓
Temporal Object Analysis
    ↓
4D Shape Descriptor Estimation
    ↓
Descriptor Comparison
    ↓
Descriptive Proximity Analysis
    ↓
One-Shot Object Recognition
```

Instead of relying solely on appearance-based classification, the system constructs a **four-dimensional temporal shape representation** for each detected moving object.

The resulting descriptor sets are compared to determine their **descriptive proximity** — how closely the characteristics of an observed object correspond to objects represented in the training data.

When multiple objects are present within the same scene, descriptors are estimated and compared for the detected objects individually.

---

## Key Contributions

* Extended moving-object shape representation into the **temporal domain**
* Developed **4D shape descriptors** for representing moving objects across video
* Addressed both **single and multiple moving-object recognition**
* Applied **descriptive proximity** to compare detected objects with training examples
* Investigated **one-shot recognition**, requiring only one training example per object class
* Evaluated recognition under changes in object viewpoint
* Evaluated multiple moving objects occurring within the same video scene
* Applied the approach to vehicle recognition in complex outdoor environments

---

## Test Scenarios

### Multiple Moving Object Recognition

This test evaluates a scene containing **multiple moving objects within the same video sequence**.

The algorithm detects individual moving objects, estimates their temporal shape descriptors, and compares their representations with the available training examples using descriptive proximity.

[View Demo](assets/demos/vehicle-test31-detection.mp4)

![Multiple moving-object recognition result](assets/results/test31-recognition-result.png)

The resulting comparisons identify objects that are **descriptively near (similar)** as well as objects that are **descriptively far (dissimilar)** based on their estimated shape characteristics.

---

### Single Object Recognition from a Different Viewpoint

This test evaluates recognition of a **single moving object observed from a viewpoint different from the available training example**.

[View Demo](assets/demos/vehicle-test36-detection.mp4)

![Different-viewpoint recognition result](assets/results/test36-recognition-result.png)

After estimating the detected object's temporal shape descriptors and applying descriptive proximity, the approach identifies the training vehicle with the closest descriptive characteristics.

This scenario evaluates whether the representation can retain useful recognition characteristics despite changes in viewpoint.

---

## Research Characteristics

| Area                 | Approach                                    |
| -------------------- | ------------------------------------------- |
| Domain               | Computer Vision / Pattern Recognition       |
| Input                | Video                                       |
| Problem              | Single & Multiple Moving Object Recognition |
| Learning Setting     | One-Shot Recognition                        |
| Training Data        | One Sample per Object Class                 |
| Representation       | Temporal 4D Shape Descriptors               |
| Matching             | Descriptor-Based Similarity                 |
| Similarity Framework | Descriptive Proximity                       |
| Application          | Moving Vehicle Recognition                  |

---

## Why This Work Is Different

The objective of this research was not to build another large-data image classifier.

Instead, it investigates whether **single and multiple moving objects can be recognized from limited training data** by using their geometric and temporal characteristics as discriminative information.

This makes the work particularly relevant to scenarios where:

* labeled training data is scarce
* only a small number of reference examples are available
* new object classes must be introduced with limited retraining data
* multiple moving objects may appear within the same scene
* temporal behavior provides useful information beyond a single image
* recognition should remain interpretable through measurable object characteristics

---

## Experimental Results

The recognition approach was evaluated on both individual moving objects and scenes containing multiple moving vehicles.

- **Single-object tests:** nearest descriptive-proximity scores ranged from **81.1% to 99.7%**
- **Multiple-object tests:** eight detected objects across four multi-object videos produced nearest descriptive-proximity scores from **90.8% to 99.9%**
- **Broader test results:** 28 of 33 reported results had nearest descriptive-proximity scores above **90%**

> Descriptive proximity represents descriptor-based similarity and should not be interpreted as conventional classification accuracy.

[View Detailed Results](docs/results.md)

---

## Repository Structure

```text
.
├── assets/
│   ├── demos/            # Video outputs from test scenarios
│   └── results/          # Recognition-result visualizations
│
├── docs/
│   ├── methodology.md    # Extended methodology documentation
│   └── results.md        # Test-case notes and results
│
├── src/                  # Research implementation
│
├── CITATION.cff
├── LICENSE
└── README.md
```

---

## Thesis

**Temporal Multiple Moving Objects Recognition Using Shape-Based Descriptor Matching**

**Juwairiah Zia**
M.Sc. Electrical and Computer Engineering
University of Manitoba, 2023

[Read the full thesis](https://mspace.lib.umanitoba.ca/items/a267fb22-720b-4493-96c1-e15bc2aefd8a)

---

## Research Areas

`Computer Vision` · `Single Object Recognition` · `Multiple Object Recognition` · `Video Analysis` · `Temporal Analysis` · `4D Shape Descriptors` · `Pattern Recognition` · `One-Shot Recognition` · `Descriptive Proximity`
