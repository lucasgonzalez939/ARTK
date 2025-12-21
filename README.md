# WebAR Visualization# WebAR 3D Model Viewer



A clean, minimal WebAR application for visualizing 3D planetary models using AR.js and A-Frame.An augmented reality web application for visualizing 3D planetary models using marker-based AR.



## Features## 🚀 Features



- 🟢 **Pattern Marker** (Hiro) - Test marker that works from screens- **Unique AR Markers Per Model**: Each model has its own barcode marker

- 🔴 **Mars** - Barcode marker 0 (requires printed marker)- **Multiple Simultaneous Models**: Display different models at the same time

- 🪐 **Jupiter** - Barcode marker 1 (requires printed marker)- **Local 3D Models**: Jupiter and Mars GLB models loaded from the `models/` folder

- 📱 Fully responsive and mobile-optimized- **Auto-Generated Marker System**: Markers are automatically created for each model

- 🎨 Clean, minimal UI with glassmorphism effects- **QR Code Sharing**: Share the app via QR code

- 📦 Expandable marker system (supports up to 32 markers)- **Marker-based Detection**: Uses AR.js Barcode markers (ID 6, 7, etc.)

- **Minimal UI**: Clean, non-invasive interface with circular icon buttons

## Setup- **Camera Permission Handling**: Proper error handling and user feedback

- **Fullscreen Mode**: Immersive AR experience

1. **Start a local server:**- **Mobile Optimized**: Touch-friendly controls

   ```bash

   python3 -m http.server 8000## 📁 Project Structure

   ```

```

2. **Open in browser:**ARTK/

   ```├── index.html                      # Main AR application

   http://localhost:8000├── guide.html                      # Visual guide (QR vs AR markers)

   ```├── markers.html                    # All available AR markers reference

├── models/                         # 3D models folder

3. **Download markers:**│   ├── Jupiter_1_142984.glb       # Jupiter model (Marker ID: 6)

   - Click the ⚙️ (Settings) button│   └── Mars_1_6792.glb            # Mars model (Marker ID: 7)

   - Download individual markers or all at once├── README.md                       # This file

   - **Print barcode markers** on white paper for best results├── QR_vs_AR_MARKERS.md            # QR vs AR comparison

└── HOW_TO_GENERATE_AR_MARKERS.md  # Complete AR marker guide

## Usage```



1. Allow camera access when prompted## 🎯 How to Use

2. Point camera at:

   - **Hiro marker** - For testing (works from screens)### 1. Setup

   - **Barcode 0** - To see Mars (print required)- Ensure all files are in the correct folder structure

   - **Barcode 1** - To see Jupiter (print required)- The app must be served via HTTP/HTTPS (not as a local file)



## Project Structure### 2. Running the App



```**Option A: Using Python (recommended for testing)**

ARTK/```bash

├── index.html              # Main AR applicationcd /home/lucas/Documentos/src/ARTK

├── models/                 # 3D GLB modelspython3 -m http.server 8000

│   ├── Mars_1_6792.glb```

│   └── Jupiter_1_142984.glbThen open: http://localhost:8000

└── markers/                # AR markers

    ├── hiro.png           # Test pattern marker**Option B: Using Node.js**

    └── 3x3_parity_6_5/    # Barcode markers (0-31)```bash

```npx serve

```

## Adding New Models

**Option C: VS Code Live Server Extension**

To add a new 3D model:- Right-click `index.html` → "Open with Live Server"



1. Add your GLB file to the `models/` folder### 3. Using the AR Experience

2. Update `markerConfig` array in `index.html`:

   ```javascript1. **Download AR Markers**

   { id: 2, model: 'YourModel', emoji: '🌍', file: 'models/your-model.glb', active: true }   - Click the Settings ⚙ button

   ```   - Scroll to "AR Markers (Per Model)"

3. Add corresponding marker in the AR scene:   - Download individual markers or click "Download All Markers"

   ```html   - **Jupiter** uses Marker ID 6

   <a-marker type="barcode" value="2">   - **Mars** uses Marker ID 7

       <a-entity

           gltf-model="models/your-model.glb"2. **Print Markers**

           position="0 0 0"   - Print markers on white paper (actual size)

           scale="0.5 0.5 0.5"   - Or display on another screen

           animation="property: rotation; to: 0 360 0; loop: true; dur: 20000; easing: linear">   - Keep markers flat and well-lit

       </a-entity>

   </a-marker>3. **Start AR**

   ```   - Click "Start AR Experience"

   - Allow camera permissions when prompted

## Technologies

4. **View Models**

- **A-Frame 1.3.0** - WebVR framework   - Point your camera at a marker

- **AR.js 3.4.7** - Augmented reality for the web   - **Marker #6** → Jupiter appears

- **THREE.js** - 3D rendering   - **Marker #7** → Mars appears

- **3x3 Barcode Markers** - Professional AR.js marker system   - Can see **BOTH models** simultaneously if both markers are visible!



## Tips5. **Controls**

   - ⛶ Button: Toggle fullscreen mode

- 🖨️ **Print markers** on white paper with good quality for best tracking   - ⚙ Button: Open settings panel

- 💡 Ensure **good lighting** when using AR   - QR Code: Share app with others

- 📏 Keep markers **flat and visible**

- 🔄 Test with **Hiro marker first** to verify AR is working## 🔧 Adding New Models

- 📱 Works best on **mobile devices** with rear cameras

To add more 3D models:

## Browser Support

1. **Add the GLB file** to the `models/` folder

- Chrome (recommended)2. **Update the JavaScript** in `index.html`:

- Firefox

- Safari (iOS)```javascript

- Edge// Add to the models object

const models = {

**Note:** Camera access requires HTTPS in production or localhost for development.    'models/Jupiter_1_142984.glb': { name: 'Jupiter', scale: '0.5 0.5 0.5', rotation: '0 0 0' },

    'models/Mars_1_6792.glb': { name: 'Mars', scale: '0.5 0.5 0.5', rotation: '0 0 0' },
    'models/YourModel.glb': { name: 'Your Model', scale: '1 1 1', rotation: '0 0 0' }
};
```

3. **Add asset in the HTML template**:

```javascript
<a-asset-item id="yourModelId" src="models/YourModel.glb"></a-asset-item>
```

4. **Add option to selector**:

```html
<option value="models/YourModel.glb">🌟 Your Model</option>
```

5. **Update the model ID logic** in the `changeModel()` function

## ⚙️ Model Configuration

Each model in the `models` object has these properties:

- **name**: Display name shown in the UI
- **scale**: Size adjustment (x y z) - adjust if model is too big/small
- **rotation**: Orientation in degrees (x y z) - useful for proper alignment

### Scale Guidelines
- Start with `1 1 1` for normal size
- Increase for smaller models (e.g., `2 2 2`)
- Decrease for larger models (e.g., `0.1 0.1 0.1`)

### Rotation Guidelines
- X-axis: Pitch (forward/backward tilt)
- Y-axis: Yaw (left/right rotation)
- Z-axis: Roll (spinning)

## 🌐 Browser Compatibility

- ✅ Chrome/Edge (Desktop & Mobile)
- ✅ Firefox (Desktop & Mobile)
- ✅ Safari (iOS 11+)
- ⚠️ Camera access requires HTTPS in production

## 📱 Mobile Tips

- Use rear camera for best results
- Ensure good lighting conditions
- Keep the marker flat and fully visible
- Hold device steady for stable tracking
- Print marker on white paper for better detection

## 🔒 Privacy

- All processing happens locally in your browser
- Camera feed is not transmitted or stored
- No data is sent to external servers
- Models are loaded from your local folder

## 🐛 Troubleshooting

**Camera not working?**
- Check browser permissions
- Use HTTPS or localhost
- Try refreshing the page

**Model not appearing?**
- Ensure marker is fully visible and well-lit
- Check browser console for loading errors
- Verify model file paths are correct

**Model too big/small?**
- Adjust the `scale` parameter in the models object
- Typical range: 0.1 to 5.0

**Model upside down?**
- Adjust the `rotation` parameter
- Try `-90 0 0` for common orientation issues

## 📚 Technologies Used

- [A-Frame](https://aframe.io/) - WebVR framework
- [AR.js](https://ar-js-org.github.io/AR.js-Docs/) - Augmented reality library
- WebGL - 3D rendering
- WebRTC - Camera access

## 📄 License

Free to use and modify for personal and commercial projects.
