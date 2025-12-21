# Quick Start Guide

## 🚀 5-Minute Setup

### 1. Start Server
```bash
cd /home/lucas/Documentos/src/ARTK
python3 -m http.server 8000
```

### 2. Open Browser
Navigate to: `http://localhost:8000`

### 3. Test AR Detection

**Option A: Test on Screen (Quick)**
1. Click ⚙️ Settings button
2. Download "Hiro Test Marker"
3. Open the image on another device/window
4. Point your camera at it
5. You should see Mars appear! ✅

**Option B: Test with Printed Markers (Production)**
1. Click ⚙️ Settings button
2. Download Mars and Jupiter markers
3. Print them on white paper
4. Point your camera at the printed markers
5. See the planets in AR!

## 📱 Mobile Testing

To test on your phone:
1. Get your computer's local IP: `hostname -I`
2. On your phone, navigate to: `http://YOUR_IP:8000`
3. Or scan the QR code in Settings

## ✅ What Should Happen

- **Green box** = Hiro marker detected
- **Red planet** = Mars detected (marker 0)
- **Large planet** = Jupiter detected (marker 1)

## ❌ Troubleshooting

**Camera not working?**
- Allow camera permissions in browser
- Make sure you're on `localhost` or HTTPS
- Try a different browser (Chrome recommended)

**Markers not detecting?**
- Ensure good lighting
- Keep marker flat and fully visible
- Move camera 30-50cm away from marker
- **Barcode markers MUST be printed** (don't work from screens)

**Models not appearing?**
- Check console for errors (F12)
- Verify models are in `models/` folder
- Try the Hiro marker first (it always works)

## 🎯 Next Steps

Once it's working:
- Print barcode markers 0 and 1 for best results
- Add more models (32 markers available!)
- Share QR code with friends
- Deploy to HTTPS server for production

---

**Need help?** Check `README.md` for full documentation.
