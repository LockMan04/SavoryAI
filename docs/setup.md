# Quick Start Guide

## System Requirements

### Minimum Requirements
- **OS**: Windows 10/11, macOS 12+, or Ubuntu 20.04+
- **RAM**: 4GB (8GB recommended)
- **Storage**: 2GB free space
- **Python**: 3.9 or higher
- **Node.js**: 16.0 or higher

### Recommended Setup
- **RAM**: 16GB for optimal AI model performance
- **GPU**: CUDA-compatible GPU for faster YOLO inference
- **Storage**: SSD for better performance

## Installation Steps

### 1. Backend Setup
```bash
# Clone and setup Python environment
git clone <repository-url>
cd food-app

# Create virtual environment
python -m venv .venv

# Activate environment
.venv\Scripts\activate  # Windows
source .venv/bin/activate  # Linux/Mac

# Install dependencies
cd api
pip install -r requirements.txt
```

### 2. Frontend Setup
```bash
# Install Node.js dependencies
cd food-app
npm install

# Start development server
npm start
```

### 3. AI Models Setup

#### YOLO Model
- Place trained model at `./models/best.pt`
- Or download pre-trained model from Ultralytics

#### LM Studio
1. Download [LM Studio](https://lmstudio.ai/)
2. Install a compatible model (recommend: gemma-2-2b or llama-3.2-3b)
3. Start local server on port 1234

#### Vector Database
- ChromaDB initializes automatically on first run
- Pre-populate with recipe data for better context

## Configuration

### Environment Variables
```bash
# Backend (.env)
YOLO_MODEL_PATH=../models/best.pt
LM_STUDIO_BASE_URL=http://localhost:1234/v1
VECTORDB_PATH=../saved_systems/recipe_rag_*/vectordb

# Frontend (.env)
REACT_APP_API_URL=http://localhost:5000
```

### Port Configuration
- **Backend API**: 5000
- **Frontend Dev**: 3000  
- **LM Studio**: 1234

## First Run

### 1. Start Backend
```bash
cd api
python main.py
```

### 2. Start Frontend  
```bash
npm start
```

### 3. Test Upload
1. Open http://localhost:3000
2. Upload a food image
3. Verify ingredient detection
4. Generate recipes
5. Test chat functionality

## Troubleshooting

### Common Issues

**"YOLO model not found"**
- Check model path in config.py
- Verify file permissions
- Download compatible model

**"LM Studio connection failed"**
- Ensure LM Studio is running
- Check port 1234 is available
- Verify model is loaded

**"Frontend won't start"**
- Clear node_modules: `rm -rf node_modules && npm install`
- Check port 3000 is available
- Update Node.js if needed

## Next Steps

1. **Customize Models**: Train YOLO with your own dataset
2. **Add Recipes**: Populate vector database with recipes
3. **Configure UI**: Customize themes and layout
4. **Deploy**: Set up production environment

## Support

For technical issues:
1. Check logs in browser console
2. Review backend terminal output
3. Verify all services are running
4. Check configuration files
