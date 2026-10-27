# VisionRange — Object Detection & Distance Estimation

A browser-based computer-vision demo that detects everyday objects from a webcam or uploaded image, draws bounding boxes, displays confidence scores, and provides approximate distance estimates using a simple monocular camera model.

## Features

- Real-time object detection using TensorFlow.js and COCO-SSD
- Webcam input and image upload
- Bounding boxes, labels, and confidence scores
- Adjustable confidence threshold
- Approximate distance estimates with configurable object width and focal length
- Responsive dashboard; inference runs in the browser
- Camera feed is not uploaded by this demo

## Live demo

After GitHub Pages deployment finishes, open: https://virojayeshpatel.github.io/Object_Detection_With_Distance/

If the page is not available yet, check the repository Actions tab for the Pages deployment workflow and ensure GitHub Pages is configured to use GitHub Actions under Settings → Pages.

## Run locally

1. Clone this repository.
2. Run `python -m http.server 8000` from the project folder.
3. Visit http://localhost:8000. Camera access requires HTTPS or localhost.

The TensorFlow.js and COCO-SSD libraries load from jsDelivr, so an internet connection is required.

## Distance estimation limitations

The demo estimates distance using: estimated distance ≈ (assumed real object width × focal length in pixels) / detected bounding-box width in pixels.

This is a monocular approximation, not a calibrated range sensor. Accuracy depends on actual object size, pose, camera field of view, crop/zoom, and bounding-box quality. Calibrate against an object at a known distance. Do not use for driving, navigation, industrial safety, or other safety-critical tasks.

## Technology

HTML, CSS, JavaScript, TensorFlow.js, and COCO-SSD.

## Privacy

Camera access is requested only after clicking Start camera. Video is processed in the browser; no application backend receives the camera feed. Model files are downloaded from the CDN.
