# Face Mapper

A web application that detects faces and maps facial expressions to LED patterns using Three.js and face-api.js.

## Features

- Real-time face detection using face-api.js
- Facial expression recognition (happy, sad, surprised, angry, neutral)
- 3D LED cube visualization with Three.js
- Responsive LED grid display
- Camera access with fallback to demo mode

## Local Development

1. Clone the repository
2. Start a local server:
   ```bash
   python -m http.server 8000
   ```
3. Open your browser to `http://localhost:8000`

## Deployment on Vercel

### Method 1: Vercel CLI (Recommended)

1. Install Vercel CLI:
   ```bash
   npm i -g vercel
   ```

2. Login to Vercel:
   ```bash
   vercel login
   ```

3. Deploy:
   ```bash
   vercel
   ```

4. Follow the prompts to configure your project

### Method 2: GitHub Integration

1. Push your code to a GitHub repository
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will automatically detect the configuration and deploy

### Method 3: Drag and Drop

1. Go to [vercel.com](https://vercel.com)
2. Drag and drop your project folder
3. Vercel will automatically deploy

## Important Notes for Deployment

- **HTTPS Required**: Camera access requires HTTPS in production
- **Models Directory**: The `/models` directory contains face-api.js models and must be included
- **Static Files**: All JavaScript modules and assets are served as static files
- **CORS Headers**: Configured in `vercel.json` for proper resource loading

## File Structure

```
├── index.html              # Main application file
├── vercel.json             # Vercel deployment configuration
├── package.json            # Project metadata
├── models/                 # Face-api.js model files
├── three.module.js         # Three.js library
├── RoundedBoxGeometry.js   # Custom Three.js geometry
├── EffectComposer.js       # Three.js post-processing
├── RenderPass.js           # Three.js render pass
├── UnrealBloomPass.js      # Three.js bloom effect
└── shaders/                # Custom shaders
```

## Browser Compatibility

- Modern browsers with WebGL support
- Camera access requires HTTPS (except localhost)
- Face detection works best with recent browser versions

## Troubleshooting

### White Screen Issues
- Check browser console for JavaScript errors
- Ensure all required files are present
- Verify HTTPS is enabled for camera access

### Camera Not Working
- Ensure you're using HTTPS in production
- Check browser permissions for camera access
- The app will fall back to demo mode if camera is unavailable

### Models Not Loading
- Verify the `/models` directory is included in deployment
- Check network tab for 404 errors on model files
- Ensure proper CORS headers are set
