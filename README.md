# Manual ROI Contouring Using Spline and Ellipse Editors in MeVisLab

## 🧠 Project Overview

This project explores **manual region of interest (ROI) contouring** in medical images using **MeVisLab**.

The goal is to understand how the Spline and Ellipse editors can be used to create and modify contours interactively on a sample brain MRI image. This is an educational medical image processing exercise.

## 🎯 Objectives

- Build an interactive contouring network in MeVisLab.
- Create contours using the Ellipse Editor.
- Create and adjust contours using the Spline Editor.
- Manage and display multiple contour objects.
- Explore the strengths and limitations of manual contouring.

## 🛠️ Tools and Data

- **Software:** MeVisLab
- **Image:** Sample brain MRI displayed using `LocalImage`
- **Methods:** Manual ROI contouring with spline and ellipse editors

## ⚙️ Modules Used

| Module | Function |
|---|---|
| `LocalImage` | Supplies the sample medical image |
| `View2D` | Displays the image and contours |
| `CSOManager` | Manages contour objects |
| `SoView2DCSOExtensibleEditor` | Supports interactive contour editing |
| `SoCSOSplineEditor` | Creates and modifies spline contours |
| `SoCSOEllipseEditor` | Creates elliptical contours |
| `SoGroup` | Combines editor extensions |

## 🔄 Workflow

1. Display the sample MRI using `LocalImage` and `View2D`.
2. Connect `CSOManager` to `SoView2DCSOExtensibleEditor`.
3. Connect `SoCSOSplineEditor` and `SoCSOEllipseEditor` through `SoGroup` to the extensible editor.
4. Connect the extensible editor to the viewer's `inInvPreLUT` input for interaction.
5. Select the editor by setting the **Creator Extension Id** to `ellipse` or `spline`.
6. Draw contours and adjust spline control points in the viewer.

## 📷 Results

- **Ellipse:** Created an elliptical practice contour by dragging in the image viewer.
- **Spline:** Created a practice contour using control points and explored manual shape adjustment.
- Displayed both contour types over the sample brain MRI.

These are **practice contours**, not validated anatomical segmentations or binary segmentation masks.

## 💡 What I Learned

- Manual contouring provides direct control over contour placement.
- Spline control points make irregular contour shapes easier to adjust.
- Ellipse editors provide a quick way to outline approximately elliptical regions.
- `CSOManager` can organize multiple contour objects.
- Manual control does not automatically imply higher segmentation accuracy; results depend on image quality and operator judgment.

## 🔍 Relation to My LiveWire Experiment

In a separate MeVisLab experiment, I explored semi-automatic LiveWire contouring using a gradient-based cost image. LiveWire struggled to follow some weak-contrast boundaries. Manual contouring helped me explore an alternative way to position contours in ambiguous regions.

**Important:** The two experiments used different images, so this is a comparison of learning experiences, **not** a controlled accuracy comparison.

## 🚀 Next Steps

- Apply LiveWire and manual contouring to the same image and region of interest.
- Explore creating binary masks from appropriately closed contours.
- Evaluate contours against reference annotations when available.

## 📁 Suggested Repository Structure

```text
Manual-ROI-Contouring-with-MeVisLab/
├── Manual_ROI_Contouring_Spline_Ellipse.mlab
├── README.md
└── screenshots/
    ├── network.png
    └── manual_contours.png
```

Screenshot filenames are examples; use the names of your actual images.

## ⚠️ Disclaimer

This project is for **education and experimentation only**. Its contours have not been clinically validated and must not be used for diagnosis.
