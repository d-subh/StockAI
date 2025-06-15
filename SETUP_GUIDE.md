# 🚀 Complete VS Code Setup Guide for StockAI

## 📋 Quick Start Checklist

- [ ] Install Node.js (v16+)
- [ ] Install Python (v3.8+)  
- [ ] Install VS Code
- [ ] Install VS Code Extensions
- [ ] Clone/Download Project
- [ ] Setup Frontend
- [ ] Setup Backend
- [ ] Test Everything

## 🛠️ Detailed Setup Instructions

### 1. Prerequisites Installation

#### Install Node.js
1. Go to [nodejs.org](https://nodejs.org/)
2. Download LTS version (v18+ recommended)
3. Run installer and follow instructions
4. Verify: Open terminal and run `node --version`

#### Install Python
1. Go to [python.org](https://python.org/)
2. Download Python 3.8+ (3.11 recommended)
3. **Important**: Check "Add Python to PATH" during installation
4. Verify: Open terminal and run `python --version`

#### Install VS Code
1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Download and install for your OS
3. Launch VS Code

### 2. VS Code Extensions Setup

Install these essential extensions:

**Required Extensions:**
- **Python** (Microsoft) - Python language support
- **ES7+ React/Redux/React-Native snippets** - React snippets
- **Tailwind CSS IntelliSense** - Tailwind CSS support

**Recommended Extensions:**
- **Auto Rename Tag** - Auto rename paired HTML tags
- **Bracket Pair Colorizer** - Colorize matching brackets
- **GitLens** - Enhanced Git capabilities
- **Thunder Client** - API testing (alternative to Postman)

### 3. Project Setup

#### Option A: Download Project Files
1. Download/extract project files to a folder
2. Open VS Code
3. File → Open Folder → Select your project folder

#### Option B: Clone from Git (if available)
```bash
git clone <repository-url>
cd stockai-ml-prediction
code .
```

### 4. Frontend Setup (React)

Open VS Code terminal (`Ctrl+`` ` or `View → Terminal`):

```bash
# Install Node.js dependencies
npm install

# Start development server
npm run dev
```

✅ **Success**: Frontend running at `http://localhost:5173`

### 5. Backend Setup (Python ML)

#### Method 1: Automated Setup (Recommended)
Open **new terminal** in VS Code (`Terminal → New Terminal`):

```bash
# Navigate to backend directory
cd ml_backend

# Run automated setup script
python run_local.py
```

#### Method 2: Manual Setup
```bash
cd ml_backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Start server
python app.py
```

✅ **Success**: Backend running at `http://localhost:5000`

### 6. VS Code Configuration

#### Set Python Interpreter
1. Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS)
2. Type "Python: Select Interpreter"
3. Choose: `./ml_backend/venv/bin/python` (or `venv\Scripts\python.exe` on Windows)

#### Verify Setup
1. **Frontend Test**: Open `http://localhost:5173` - Should see StockAI dashboard
2. **Backend Test**: Open `http://localhost:5000/api/health` - Should see JSON response
3. **Integration Test**: Search for "AAPL" or "Tesla" in the frontend

## 🎯 VS Code Workflow Tips

### Terminal Management
- **Split Terminal**: Click the split icon in terminal
- **Multiple Terminals**: Run frontend and backend simultaneously
- **Terminal Shortcuts**: 
  - `Ctrl+`` ` - Toggle terminal
  - `Ctrl+Shift+`` ` - New terminal

### Debugging
- **Python Debugging**: Set breakpoints in Python files, press F5
- **Console Logs**: Check browser console for frontend issues
- **Network Tab**: Monitor API calls in browser DevTools

### File Navigation
- **Quick Open**: `Ctrl+P` - Quickly open any file
- **Go to Symbol**: `Ctrl+Shift+O` - Navigate to functions/classes
- **File Explorer**: `Ctrl+Shift+E` - Toggle file explorer

## 🔧 Troubleshooting

### Common Issues & Solutions

#### 1. "Python not found"
```bash
# Try these alternatives:
python3 --version
py --version

# Add Python to PATH (Windows):
# Search "Environment Variables" → Edit PATH → Add Python installation folder
```

#### 2. "pip not found"
```bash
# Install pip:
python -m ensurepip --upgrade

# Or use:
python -m pip --version
```

#### 3. "Permission denied" (macOS/Linux)
```bash
# Use python3 instead of python:
python3 -m venv venv
source venv/bin/activate
```

#### 4. "Port already in use"
```bash
# Frontend (change port):
npm run dev -- --port 3000

# Backend (edit ml_backend/app.py):
app.run(debug=True, port=5001)
```

#### 5. "Module not found" errors
```bash
# Reinstall dependencies:
cd ml_backend
pip install --upgrade pip
pip install -r requirements.txt
```

#### 6. TensorFlow installation issues
```bash
# Install CPU-only version:
pip install tensorflow-cpu

# Or skip TensorFlow (LSTM model will be disabled):
# Comment out tensorflow in requirements.txt
```

## 🧪 Testing Your Setup

### 1. API Testing with VS Code

Install **Thunder Client** extension, then:

1. Create new request
2. Method: POST
3. URL: `http://localhost:5000/api/predict`
4. Body (JSON):
```json
{
  "symbol": "AAPL"
}
```
5. Send request - should get ML prediction response

### 2. Frontend Testing

1. Open `http://localhost:5173`
2. Search for stocks: "Apple", "Tesla", "LIC", "Tata Motors"
3. Click on search results to see detailed predictions
4. Navigate through different tabs (Dashboard, Predictions, Portfolio)

### 3. Integration Testing

1. Search for "AAPL" in frontend
2. Check browser Network tab - should see API call to backend
3. Verify prediction data appears in UI

## 📊 Development Workflow

### Recommended Daily Workflow

1. **Start VS Code**: Open project folder
2. **Start Servers**: 
   - Terminal 1: `npm run dev` (Frontend)
   - Terminal 2: `cd ml_backend && python app.py` (Backend)
3. **Development**: Make changes, see live updates
4. **Testing**: Test features in browser
5. **Debugging**: Use VS Code debugger for Python, browser DevTools for React

### File Structure Understanding

```
stockai-ml-prediction/
├── src/                     # React frontend source
│   ├── components/         # React components
│   ├── hooks/             # Custom React hooks
│   ├── types/             # TypeScript types
│   └── data/              # Mock data
├── ml_backend/             # Python ML backend
│   ├── ml_models/         # ML model implementations
│   ├── data_processing/   # Data fetching and processing
│   ├── app.py            # Flask server
│   └── requirements.txt   # Python dependencies
├── package.json           # Node.js dependencies
└── README.md             # Project documentation
```

## 🚀 Next Steps

Once everything is running:

1. **Explore the Code**: Understand the React components and Python ML models
2. **Customize**: Add your own stocks, modify UI, improve ML models
3. **Extend**: Add new features like portfolio tracking, alerts, etc.
4. **Deploy**: Consider deploying to cloud platforms

## 🆘 Getting Help

If you're stuck:

1. **Check Terminal Output**: Look for error messages in both terminals
2. **Browser Console**: Check for JavaScript errors (F12 → Console)
3. **Python Errors**: Check the Python terminal for stack traces
4. **Network Issues**: Verify both servers are running on correct ports
5. **Dependencies**: Ensure all packages are installed correctly

## 📞 Support Commands

```bash
# Check versions
node --version
python --version
npm --version
pip --version

# Reinstall everything
npm cache clean --force
rm -rf node_modules package-lock.json
npm install

cd ml_backend
rm -rf venv
python -m venv venv
# Activate venv, then:
pip install -r requirements.txt
```

**You're all set! Happy coding! 🎉**