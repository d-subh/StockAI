# 🚀 StockAI - ML Stock Market Prediction Platform

A full-stack application with React frontend and Python ML backend for intelligent stock market predictions.

## 📋 Prerequisites

Before running this project, make sure you have:

- **Node.js** (v16 or higher) - [Download here](https://nodejs.org/)
- **Python** (v3.8 or higher) - [Download here](https://python.org/)
- **VS Code** - [Download here](https://code.visualstudio.com/)
- **Git** (optional but recommended)

## 🛠️ VS Code Setup

### 1. Install Required VS Code Extensions

Open VS Code and install these extensions:

- **Python** (by Microsoft)
- **ES7+ React/Redux/React-Native snippets**
- **Tailwind CSS IntelliSense**
- **Auto Rename Tag**
- **Bracket Pair Colorizer**
- **GitLens** (optional)

### 2. Clone/Download the Project

If you have the project files:
```bash
# Navigate to your desired directory
cd your-projects-folder

# If using Git
git clone <your-repo-url>
cd stockai-ml-prediction

# Or simply extract the project files to a folder
```

### 3. Open Project in VS Code

```bash
# Open the project folder in VS Code
code .

# Or open VS Code and use File > Open Folder
```

## 🎯 Project Structure

```
stockai-ml-prediction/
├── src/                    # React frontend
├── ml_backend/            # Python ML backend
├── package.json           # Node.js dependencies
├── tailwind.config.js     # Tailwind CSS config
├── vite.config.ts         # Vite configuration
└── README.md             # This file
```

## 🚀 Running the Project

### Step 1: Setup Frontend (React)

Open VS Code terminal (`Ctrl+`` ` or `View > Terminal`) and run:

```bash
# Install Node.js dependencies
npm install

# Start the React development server
npm run dev
```

The frontend will be available at: `http://localhost:5173`

### Step 2: Setup Python ML Backend

Open a **new terminal** in VS Code (`Terminal > New Terminal`) and run:

```bash
# Navigate to ML backend directory
cd ml_backend

# Create Python virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install Python dependencies
pip install -r requirements.txt

# Start the ML backend server
python app.py
```

The ML backend will be available at: `http://localhost:5000`

### Step 3: Verify Everything is Working

1. **Frontend**: Open `http://localhost:5173` - you should see the StockAI dashboard
2. **Backend**: Open `http://localhost:5000/api/health` - you should see a health check response
3. **Integration**: Try searching for stocks like "AAPL", "TSLA", "LIC" in the frontend

## 🔧 VS Code Configuration

### Python Interpreter Setup

1. Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS)
2. Type "Python: Select Interpreter"
3. Choose the interpreter from your virtual environment:
   - Windows: `./ml_backend/venv/Scripts/python.exe`
   - macOS/Linux: `./ml_backend/venv/bin/python`

### Recommended VS Code Settings

Create `.vscode/settings.json` in your project root:

```json
{
  "python.defaultInterpreterPath": "./ml_backend/venv/bin/python",
  "python.terminal.activateEnvironment": true,
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": true
  },
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

## 🐛 Troubleshooting

### Common Issues and Solutions

#### 1. Python Dependencies Installation Failed
```bash
# Upgrade pip first
python -m pip install --upgrade pip

# Install dependencies one by one if batch install fails
pip install flask flask-cors
pip install pandas numpy scikit-learn
pip install tensorflow
pip install yfinance ta
```

#### 2. Node.js Dependencies Issues
```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

#### 3. Port Already in Use
```bash
# Frontend (if port 5173 is busy)
npm run dev -- --port 3000

# Backend (if port 5000 is busy)
# Edit ml_backend/app.py and change the port:
app.run(debug=True, host='0.0.0.0', port=5001)
```

#### 4. CORS Issues
Make sure both servers are running:
- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`

#### 5. Python Virtual Environment Issues
```bash
# If virtual environment creation fails
python3 -m venv venv  # Try python3 instead of python

# If activation fails on Windows
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## 📊 API Testing

### Test ML Predictions

You can test the ML backend directly:

```bash
# Test single stock prediction
curl -X POST http://localhost:5000/api/predict \
  -H "Content-Type: application/json" \
  -d '{"symbol": "AAPL"}'

# Test batch predictions
curl -X POST http://localhost:5000/api/batch_predict \
  -H "Content-Type: application/json" \
  -d '{"symbols": ["AAPL", "TSLA", "LICI"]}'

# Check model status
curl http://localhost:5000/api/model_status
```

## 🎨 Development Workflow

### Recommended VS Code Workflow

1. **Split Terminal**: Use split terminal to run both frontend and backend
2. **File Explorer**: Use `Ctrl+Shift+E` to navigate files quickly
3. **Quick Open**: Use `Ctrl+P` to quickly open files
4. **Integrated Debugging**: Set breakpoints in Python code for debugging
5. **Git Integration**: Use built-in Git features for version control

### Hot Reloading

- **Frontend**: Automatically reloads on file changes
- **Backend**: Restart required for changes (or use `flask run` with debug mode)

## 🔍 Key Features to Test

1. **Stock Search**: Search for "Apple", "Tesla", "LIC", "Tata Motors"
2. **ML Predictions**: Get buy/sell/hold recommendations
3. **Real-time Data**: Watch live price updates
4. **Portfolio Tracking**: View portfolio performance
5. **Market Analysis**: Check technical and sentiment scores

## 📈 Next Steps

Once everything is running:

1. **Customize Stocks**: Add more stocks to the database
2. **Improve Models**: Retrain ML models with more data
3. **Add Features**: Implement additional technical indicators
4. **Deploy**: Consider deployment to cloud platforms

## 🆘 Getting Help

If you encounter issues:

1. Check the terminal output for error messages
2. Verify all dependencies are installed correctly
3. Ensure both servers are running on correct ports
4. Check the browser console for frontend errors
5. Review the Python console for backend errors

## 📞 Support

For additional help:
- Check the detailed logs in both terminals
- Verify Python and Node.js versions
- Ensure all required ports are available
- Review the API documentation in `ml_backend/README.md`

---

**Happy Coding! 🚀**