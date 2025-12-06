# CogniCare - Dementia Detection & Cognitive Assessment Platform

##  Live Demo & Media

###  Application Screenshots
**[View Webapp Screenshots & Interface Images →](https://drive.google.com/drive/folders/1A6JuuNhLb6qfsO8PvLAqd7NuXf6xitbM?usp=sharing)**  
*Complete visual walkthrough of the application interface, assessment flows, and dashboard features*

###  Video Demonstration  
**[Watch Full Demo Video →](https://drive.google.com/file/d/1VfTSgx-B3k3PyoK_axzRrsOh0ta2s8jg/view?usp=drive_link)**  
*Comprehensive demonstration of all assessment modules and platform capabilities*
###  Presentation Slides
**PPT Google Drive link**: [View Presentation](https://drive.google.com/file/d/1cQcFOl8MFlLeeuqNA8azixB1A1Kk13ih/view?usp=share_link)


---

## Project Overview

CogniCare is a comprehensive web-based platform for early detection of cognitive impairment and dementia using scientifically-validated neuropsychological assessments combined with advanced machine learning analysis. The platform provides healthcare professionals with tools to conduct standardized cognitive assessments and analyze language patterns for potential indicators of Alzheimer's disease and related dementias.

## Key Features

###  Comprehensive Assessment Battery
- **Memory Recall Test** - Evaluates short-term and long-term memory with word list exercises
- **Verbal Fluency Assessment** - Tests language abilities and cognitive flexibility 
- **Trail Making Test** - Assesses visual attention and executive function
- **Stroop Color Test** - Measures cognitive inhibition and processing speed
- **Cookie Theft Picture Description** - Analyzes language and scene description capabilities

### AI-Powered Analysis
- Advanced NLP models for analyzing speech patterns and linguistic features
- Machine learning algorithms trained to detect early signs of cognitive impairment
- Confidence scoring and risk level assessment
- Clinical interpretation and recommendations

###  Clinical Dashboard
- Patient management and assessment tracking
- Progress monitoring over time
- Comprehensive reporting and data visualization
- Secure authentication and authorization

###  CogniCare Cognitive Composite Score (CCS)
- Scientifically-validated composite scoring system
- Population norm-based Z-score calculations
- Risk stratification (healthy, mild concern, strong indication)
- Detailed domain-specific analysis

## Project Structure

```
cognicare/
├── frontend/                    # React TypeScript Frontend
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   │   ├── ui/            # shadcn/ui components
│   │   │   ├── AssessmentCard.tsx
│   │   │   ├── CogniCareResults.tsx
│   │   │   ├── MayaAvatar.tsx  # AI assistant avatar
│   │   │   └── ProtectedRoute.tsx
│   │   ├── pages/             # Main application pages
│   │   │   ├── Dashboard.tsx   # Main dashboard
│   │   │   ├── Login.tsx      # Authentication
│   │   │   ├── Register.tsx   # User registration
│   │   │   ├── ComprehensiveAssessment.tsx  # Full battery
│   │   │   ├── MemoryAssessment.tsx
│   │   │   ├── VerbalFluencyAssessment.tsx
│   │   │   ├── TrailMakingAssessment.tsx
│   │   │   ├── StroopColorAssessment.tsx
│   │   │   ├── CookieTheftAssessment.tsx
│   │   │   └── NotFound.tsx
│   │   ├── contexts/          # React contexts
│   │   │   └── AuthContext.tsx
│   │   ├── hooks/             # Custom React hooks
│   │   └── lib/               # Utility functions
│   ├── public/                # Static assets
│   ├── package.json
│   ├── vite.config.ts
│   ├── tailwind.config.ts
│   └── components.json        # shadcn/ui configuration
│
├── backend/                    # FastAPI Python Backend
│   ├── main.py                # FastAPI application entry point
│   ├── database.py            # Database configuration and connection
│   ├── models.py              # SQLAlchemy database models
│   ├── schemas.py             # Pydantic request/response schemas
│   ├── auth.py                # Authentication and authorization
│   ├── nlp_service.py         # ML/NLP analysis service
│   ├── init_db.py             # Database initialization script
│   ├── start.py               # Development server startup script
│   ├── requirements.txt       # Python dependencies
│   ├── .env.template          # Environment variables template
│   └── model_files/           # ML model artifacts (*.pkl files)
│       ├── model_control.pkl  # Control group classifier
│       ├── model_alz.pkl      # Alzheimer's classifier
│       └── vectorizer.pkl     # Text vectorizer
│
└── README.md                  # This file
```

## Technology Stack

### Frontend Technologies
- **React 18.3.1** - Modern UI framework with hooks and context
- **TypeScript 5.8.3** - Type-safe JavaScript development
- **Vite 5.4.19** - Fast build tool and development server
- **Tailwind CSS 3.4.17** - Utility-first CSS framework
- **shadcn/ui** - High-quality, accessible component library built on Radix UI
- **React Router 6.30.1** - Client-side routing and navigation
- **React Query (TanStack)** - Server state management and caching
- **React Hook Form** - Performant forms with minimal re-renders
- **Axios** - HTTP client for API communication
- **Lucide React** - Beautiful, customizable SVG icons
- **Recharts** - Composable charting library for data visualization

### Backend Technologies
- **FastAPI** - Modern, fast web framework for building APIs
- **Python 3.8+** - Programming language for backend development
- **SQLAlchemy** - SQL toolkit and Object-Relational Mapping (ORM)
- **SQLite** - Lightweight, file-based database (configurable to PostgreSQL)
- **Pydantic** - Data validation using Python type annotations
- **JWT (PyJWT)** - JSON Web Token authentication
- **Passlib & bcrypt** - Password hashing and verification
- **Uvicorn** - ASGI server for running FastAPI applications

### Machine Learning & NLP
- **scikit-learn** - Machine learning algorithms and data preprocessing
- **spaCy** - Advanced NLP library for text processing
- **NLTK** - Natural Language Toolkit for linguistic analysis
- **pickle/dill** - Model serialization and deserialization
- **regex** - Advanced pattern matching for text processing

### Development Tools
- **ESLint** - JavaScript/TypeScript linting
- **Prettier** - Code formatting
- **Git** - Version control system

## Getting Started

### Prerequisites
- **Node.js 18+** and npm (for frontend)
- **Python 3.8+** and pip (for backend)
- **Git** (for version control)

### Backend Setup

1. **Navigate to backend directory**
   ```bash
   cd backend
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download spaCy language model**
   ```bash
   python -m spacy download en_core_web_sm
   ```

4. **Set up environment variables**
   ```bash
   cp .env.template .env
   # Edit .env file with your configuration
   ```

5. **Add ML model files**
   Place the required machine learning model files in the backend directory:
   - `model_control.pkl` - Control group classifier
   - `model_alz.pkl` - Alzheimer's detection model  
   - `vectorizer.pkl` - Text feature vectorizer

6. **Initialize database**
   ```bash
   python init_db.py demo
   ```

7. **Start development server**
   ```bash
   python start.py
   ```
   *Backend will be available at http://localhost:8000*

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```
   *Frontend will be available at http://localhost:8080*

### Quick Setup Script

For automated backend setup:
```bash
cd backend
python start.py setup  # Complete environment setup
python start.py         # Start development server
python start.py check   # Verify system requirements
```

##  Configuration

### Environment Variables (.env)

```env
# Database Configuration
DATABASE_URL=sqlite:///./dementia_detection.db

# JWT Configuration  
SECRET_KEY=your-secret-key-change-this-in-production
ACCESS_TOKEN_EXPIRE_MINUTES=1440

# API Configuration
API_HOST=0.0.0.0
API_PORT=8000

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:8080
```

<!-- ### Database Configuration

The application uses SQLite by default but can be configured for PostgreSQL:

```python
# For PostgreSQL
DATABASE_URL=postgresql://username:password@localhost/dbname
``` -->

## API Testing with Postman

### Quick Setup

1. **Download Postman**
   - Visit: https://www.postman.com/downloads/
   - Install and open Postman

2. **Import Test Collection**
   - In Postman, click **Import** button
   - Select `backend/tests/CogniCare_Tests.postman_collection.json`

3. **Import Environment** 
   - Click **Environments** tab → **Import**
   - Select `backend/tests/CogniCare_Local.postman_environment.json`
   - Select "CogniCare Local" from environment dropdown (top-right)

### Running Tests

**Make sure your backend is running first:**
```bash
cd backend
python start.py
```

**Then in Postman:**

#### Run All Tests (Recommended)
# In Postman:
# 1. Import both files from src/backend/tests/
# 2. Select "CogniCare Local" environment
# 3. Click "Run" on collection

Expected result: **4/4 tests passed**

#### Run Individual Tests
Click each test in sequence:
1. **Health Check** - Verify API is running
2. **Register User** - Create test user account
3. **Login** - Get JWT token (auto-saved to environment)
4. **NLP Demo - Alzheimer's Detection** - Test ML/NLP prediction

### Test Coverage

| Test | Endpoint | What It Tests |
|------|----------|---------------|
| 1. Health Check | `GET /` | API is running |
| 2. Register User | `POST /auth/register` | User creation |
| 3. Login | `POST /auth/token` | JWT authentication |
| 4. NLP Demo | `POST /nlp/demo` | **ML/NLP Alzheimer's detection** |

### What Gets Tested

 **API Health** - Server connectivity  
 **Authentication** - User registration and JWT tokens  
 **ML/NLP Models** - Dementia detection analysis  
 **Linguistic Features** - Text processing and analysis  
 **Risk Assessment** - Clinical interpretation  

### Troubleshooting

**Tests failing?**
- Ensure backend is running: `python start.py`
- Check it's on port 8000: http://localhost:8000
- Verify ML models are in `backend/model_files/`

**Register test failing?**
- If you already registered this user, change email in Test 2
- Or delete database and restart: `python init_db.py demo`

**First time running?**
- Run tests in order (1 → 2 → 3 → 4)
- Test 3 auto-saves auth token for future use

---
##  API Endpoints

### Authentication
- `POST /auth/register` - User registration
- `POST /auth/token` - Login and token generation
- `GET /auth/me` - Get current user profile

### Patient Management  
- `POST /patients` - Create new patient
- `GET /patients` - List patients for current doctor
- `GET /patients/{id}` - Get specific patient details

### Assessments
- `POST /assessments` - Create new assessment
- `GET /assessments/{id}` - Get assessment details
- `PUT /assessments/{id}` - Update assessment results

### NLP Analysis
- `POST /nlp/analyze` - Analyze text for cognitive indicators
- `GET /nlp/analysis/{id}` - Get analysis results
- `GET /patients/{id}/progress` - Get patient progress over time

### System
- `GET /` - API health check
- `GET /health` - Detailed system status

##  Development Commands

### Backend Commands
```bash
# Setup and start
python start.py setup      # Complete environment setup
python main.py           # Start development server  
python start.py check     # System health check

# Database management
python init_db.py init    # Initialize database tables
python init_db.py demo    # Create demo data
python init_db.py reset   # Reset database (⚠️ deletes all data)
```

### Frontend Commands
```bash
npm run dev               # Start development server
npm run build             # Build for production
npm run build:dev         # Build for development
npm run preview           # Preview production build
npm run lint              # Run ESLint checks
```

##  User Roles & Permissions

### Admin
- Full system access and configuration
- User management and system monitoring
- Data export and reporting capabilities

### Doctor/Clinician  
- Patient management and assessment administration
- View patient results and progress tracking
- Generate clinical reports

### Researcher
- Access aggregated, anonymized data
- Export data for research purposes
- Statistical analysis and reporting

##  Troubleshooting

### Common Issues

**Backend won't start**
- Verify Python 3.8+ is installed
- Check all ML model files are present
- Ensure spaCy English model is downloaded: `python -m spacy download en_core_web_sm`

**Frontend build errors**
- Clear node_modules: `rm -rf node_modules && npm install`
- Check Node.js version (18+ required)
- Verify all dependencies are installed

**Database connection issues**
- Check database file permissions
- Verify DATABASE_URL in .env file
- Run database initialization: `python init_db.py demo`

**ML model loading errors**
- Ensure model files are in backend directory
- Check file permissions and formats
- Verify scikit-learn version compatibility

##  Assessment Details

### 1. Memory Recall Test (10-15 min)
- **Purpose**: Evaluates immediate and delayed memory recall
- **Method**: Word list learning with immediate and delayed recall tasks
- **Scoring**: Number of words correctly recalled
- **Population Norm**: Mean 12.5 ± 2.8 words

### 2. Verbal Fluency Assessment (5 min)
- **Purpose**: Tests semantic memory and executive function
- **Method**: Generate words from specific categories (e.g., animals)
- **Scoring**: Number of valid, unique words produced
- **Population Norm**: Mean 18.2 ± 4.3 words

### 3. Trail Making Test (8-12 min)
- **Purpose**: Assesses visual attention and task switching
- **Method**: Connect numbered and lettered circles in sequence
- **Scoring**: Time to completion for Part B
- **Population Norm**: Mean 75.0 ± 25.0 seconds

### 4. Stroop Color Test (8-10 min)
- **Purpose**: Measures cognitive inhibition and processing speed
- **Method**: Name colors while ignoring word content
- **Scoring**: Interference effect calculation
- **Population Norm**: Mean 650 ± 180 ms interference

### 5. Cookie Theft Picture Description (5-8 min)
- **Purpose**: Evaluates language production and cognitive processing
- **Method**: Describe complex picture scene
- **Scoring**: Information units and linguistic analysis
- **Population Norm**: Mean 14.5 ± 3.2 information units

##  Machine Learning Pipeline

### NLP Analysis Process
1. **Text Preprocessing**
   - Tokenization and normalization
   - POS tagging and grammatical analysis
   - Feature extraction (linguistic patterns, word frequency)

2. **Model Prediction**
   - Dual-model approach (Control vs. Alzheimer's)
   - Confidence scoring and risk assessment
   - Clinical interpretation generation

3. **Feature Analysis**
   - Word count and sentence structure
   - Lexical diversity and semantic content
   - Grammatical complexity metrics

##  Security Features

- **JWT-based authentication** with secure token handling
- **Password hashing** using bcrypt with salt
- **Role-based access control** (Admin, Doctor, Researcher)
- **CORS protection** for API endpoints
- **Input validation** using Pydantic schemas
- **SQL injection protection** via SQLAlchemy ORM