# Object Detection

A real-time object detection web application using TensorFlow.js and the COCO-SSD pre-trained model.

## Overview

This project provides a simple yet powerful tool for detecting objects in real-time using your webcam. It leverages the COCO-SSD (Common Objects in Context - Single Shot MultiBox Detector) pre-trained model to identify and classify objects with a confidence score above 66%.

## Features

- **Real-time Detection**: Process video frames from your webcam in real-time
- **Pre-trained Model**: Uses the COCO-SSD model from TensorFlow for accurate object detection
- **Confidence Scoring**: Displays detection confidence percentage for each identified object
- **Visual Highlighting**: Draws bounding boxes around detected objects
- **Browser-based**: No backend server required - runs entirely in your browser

## Technology Stack

- **TensorFlow.js**: Machine learning library for JavaScript
- **COCO-SSD Model**: Pre-trained object detection model
- **HTML5**: Video and Canvas APIs for webcam integration
- **CSS3**: Styling and layout
- **JavaScript (ES6)**: Core application logic

## How It Works

1. **Model Loading**: The COCO-SSD model is loaded from TensorFlow.js CDN when the page loads
2. **Webcam Access**: Users click the "Enable Webcam" button to grant camera access
3. **Real-time Prediction**: Frames from the webcam are continuously analyzed
4. **Object Detection**: The model detects objects and returns predictions with:
   - Object class (e.g., person, dog, car)
   - Confidence score (0-1)
   - Bounding box coordinates
5. **Visualization**: Objects with >66% confidence are highlighted with boxes and labeled with class and confidence percentage

## Getting Started

### Prerequisites

- Modern web browser with WebGL support (Chrome, Firefox, Safari, Edge)
- Webcam access permission

### Installation

1. Clone the repository:
```bash
git clone https://github.com/rastar12/objectDetection.git
cd objectDetection
```

2. Open the project in a browser:
   - Simply open `index.html` in your web browser, or
   - Use a local server (recommended):
   ```bash
   python -m http.server 8000
   # or with Python 3
   python3 -m http.server 8000
   ```
   Then navigate to `http://localhost:8000`

## Usage

1. Open the application in your browser
2. Click the "Enable Webcam" button
3. Grant camera access when prompted
4. Objects in your camera view will be detected and highlighted in real-time
5. Each detected object displays:
   - A bounding box
   - Object class name
   - Confidence percentage

## File Structure

- `index.html` - Main HTML file with UI structure
- `script.js` - JavaScript logic for model loading, webcam access, and object detection
- `style.css` - Styling for the application
- `README.md` - Project documentation

## Key Functions

### `getUserMediaSupported()`
Checks if the browser supports webcam access via the MediaDevices API

### `enableCam(event)`
Requests webcam access and initiates the detection stream

### `predictWebcam()`
Continuously processes video frames and performs object detection:
- Clears previous predictions from UI
- Runs the model on current video frame
- Filters results by confidence threshold (66%)
- Draws bounding boxes and labels for detected objects
- Schedules next frame analysis

## Supported Objects

The COCO-SSD model can detect 80+ common object classes including:
- People (person)
- Animals (dog, cat, bird, etc.)
- Vehicles (car, bus, truck, etc.)
- Household items (chair, table, etc.)
- And many more...

## Configuration

To adjust the confidence threshold, modify the value in `script.js` line 71:
```javascript
if (predictions[n].score > 0.66) {  // Change 0.66 to desired threshold
```

## Browser Compatibility

- Chrome 76+
- Firefox 79+
- Safari 14+
- Edge 79+

**Note**: Requires WebGL support for optimal performance

## Performance Notes

- Model loading takes a few seconds on first load
- Detection runs at approximately 20-30 FPS depending on hardware
- Best performance on desktop with dedicated GPU
- Mobile devices may experience slower performance

## Limitations

- Requires HTTPS or localhost to access webcam
- Performance depends on device hardware
- Best results with well-lit environments
- Confidence threshold of 66% may miss some objects or include false positives

## Future Enhancements

- Add adjustable confidence threshold slider
- Support for multiple detection models
- Recording and exporting detection results
- Mobile optimization
- Performance monitoring metrics

## License

This project is open source and available under the MIT License.

## Resources

- [TensorFlow.js Documentation](https://js.tensorflow.org/)
- [COCO-SSD Model](https://github.com/tensorflow/tfjs-models/tree/master/coco-ssd)
- [MediaDevices API](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices)

## Contributing

Contributions are welcome! Feel free to fork this repository and submit pull requests.

---

Built with ❤️ using TensorFlow.js