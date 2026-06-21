# Interface Design — Orthopedic X-ray Fracture Detection App

## Step 1. Purpose

The application helps clinicians screen X-rays for fractures. It uses AI to flag suspicious regions and speed up first-pass review.

## Step 2. Users' objectives

**Users:** Radiologists, orthopedists, ER doctors.

**Basic scenario:**
1. User uploads an X-ray.
2. System returns a label: Fracture Suspected / Review Recommended / No Fracture.
3. System shows a Grad-CAM heatmap overlay.

**Advanced scenario:**
1. User toggles language (EN/RU).
2. User views session history of past predictions.
3. User compares Grad-CAM, Grad-CAM++, Eigen-CAM views.
4. User uses demo mode (no upload) to test the system.

## Step 3. Wireframes

Two schematic wireframes were created: the upload screen and the results screen. They show layout, key elements, and content type without color or final styling.

- Upload screen: header, title, drop zone, analyze button, history panel, about section.
- Results screen: verdict badge, confidence bar, fracture/normal score pills, Grad-CAM heatmap, quality check, report grid.

(See attached wireframe image.)

## Step 4. Mockup

A static mockup was built in Figma. It applies the final shapes, fonts, colors, and navigation on top of the wireframes.

Link: https://www.figma.com/make/sh1kh0kFOQI19uiBqcra1r/Prototype-for-X-ray-Analysis-App?p=f&fullscreen=1

## Step 5. Prototype

An interactive prototype was built from the mockup in Figma. It reflects user actions and results for the basic scenario: upload an image, click analyze, see a result.

Same link as Step 4.

## Step 6. Testing and changes

Testing was done by walking through both scenarios.

- Basic scenario: upload → analyze → result shown. Works as expected.
- Advanced scenario: language toggle, history list. Works as expected.

**Gap found:** the Figma mockup/prototype did not include the EN/RU language toggle or the Grad-CAM heatmap result. These were missing because Figma could not run real model output. Both were added in the HTML/JS version in Step 7, where real backend responses are available.

## Step 7. HTML version

The prototype was converted into a working HTML page. It calls the real `/predict` API endpoint and opens in any browser without errors or overlaps.

Implemented for both scenarios:
- Basic: upload, analyze, view label, confidence score, and Grad-CAM heatmap.
- Advanced: EN/RU toggle, recent analyses history, demo mode banner when no model is loaded.

(See attached index.html file.)
