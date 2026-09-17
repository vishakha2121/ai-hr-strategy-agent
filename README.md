<div align="center">

# 🚀 AI Enterprise HR Strategy Agent

### *Transforming Workforce Data into Strategic Decisions with ML & LLMs*

An AI-powered HR intelligence platform that analyzes workforce trends, predicts hiring demand, recommends training programs, and supports organizational planning.

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org)
[![Gemini](https://img.shields.io/badge/Google-Gemini%20API-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)
[![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#️-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Database Schema](#️-database-schema)
- [API Endpoints](#-api-endpoints)
- [Installation & Setup](#-installation--setup)
- [Environment Variables](#-environment-variables)
- [Usage](#-usage)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Author](#-author)
- [License](#-license)

---

## 🔍 Overview

The **AI Enterprise HR Strategy Agent** is an intelligent HR platform designed to help organizations make data-driven workforce decisions. It combines:

- 📊 **HR Analytics** — Deep insights from employee data
- 🔮 **Predictive ML** — Forecast future hiring demand & attrition
- 🤖 **LLM-Powered Recommendations** — Personalized training & strategy reports via Google Gemini
- 📈 **Interactive Dashboard** — Beautiful visualizations for decision-makers

Whether you're an HR manager planning next quarter's hiring or an executive crafting long-term workforce strategy, this agent provides the intelligence you need.

---

## ✨ Features

### 📊 Workforce Analytics
- Employee distribution by department, role, and experience
- Attrition rate analysis with trends
- Salary benchmarking and insights
- Performance score distribution

### 🔮 Predictive ML
- **Hiring Demand Forecast** — Predicts hires needed for the next 6 months
- **Attrition Prediction** — Identifies employees at risk of leaving
- **Department-wise Demand** — Custom predictions per team

### 🎓 LLM Training Recommendations
- Personalized training programs based on skill gaps
- Career path suggestions
- Learning resource recommendations
- Powered by Google Gemini API

### 📋 Organizational Strategy Reports
- Auto-generated quarterly strategy reports
- AI-driven insights for leadership
- Actionable recommendations
- Exportable summaries

### 👥 Employee Management
- Full CRUD operations
- Search & filter employees
- Bulk CSV import
- Skill tracking

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend** | React 18 + Vite | Fast, modern UI |
| **Styling** | Tailwind CSS | Utility-first CSS |
| **Charts** | Recharts | Interactive data viz |
| **Icons** | Lucide React | Beautiful icons |
| **Routing** | React Router v6 | Client-side routing |
| **HTTP Client** | Axios | API calls |
| **Backend** | FastAPI | High-performance Python API |
| **Server** | Uvicorn | ASGI server |
| **ORM** | SQLAlchemy | Database abstraction |
| **Validation** | Pydantic | Data validation |
| **Database** | SQLite | Lightweight, file-based DB |
| **ML** | Scikit-learn | Predictive models |
| **Data** | Pandas, NumPy | Data processing |
| **LLM** | Google Gemini API | AI recommendations |
| **ML Persistence** | Joblib | Model serialization |

---

## 🏗️ Architecture



---

## 🗄️ Database Schema

### `employees`
| Column | Type | Description |
|--------|------|-------------|
| id | INTEGER | Primary Key |
| name | TEXT | Employee name |
| email | TEXT | Unique email |
| department | TEXT | Dept name |
| role | TEXT | Job title |
| salary | FLOAT | Annual salary |
| join_date | DATE | Joining date |
| experience_years | FLOAT | Total experience |
| performance_score | FLOAT | 0-10 score |
| attrition | INTEGER | 0 or 1 |
| skills | TEXT | Comma-separated |

### `departments`
| Column | Type |
|--------|------|
| id | INTEGER |
| name | TEXT |
| head_count | INTEGER |
| budget | FLOAT |

### `hiring_history`
| Column | Type |
|--------|------|
| id | INTEGER |
| month | INTEGER |
| year | INTEGER |
| hires_count | INTEGER |
| department | TEXT |

### `training_records`
| Column | Type |
|--------|------|
| id | INTEGER |
| employee_id | INTEGER |
| program_name | TEXT |
| status | TEXT |
| completion_date | DATE |

### `predictions`
| Column | Type |
|--------|------|
| id | INTEGER |
| type | TEXT |
| input_json | TEXT |
| output_json | TEXT |
| created_at | DATETIME |

### `strategy_reports`
| Column | Type |
|--------|------|
| id | INTEGER |
| report_text | TEXT |
| generated_at | DATETIME |

---

## 🌐 API Endpoints

### 👥 Employees
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/employees` | List all employees |
| GET | `/api/employees/{id}` | Get one employee |
| POST | `/api/employees` | Create employee |
| PUT | `/api/employees/{id}` | Update employee |
| DELETE | `/api/employees/{id}` | Delete employee |

### 📊 Analytics
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/analytics/overview` | Dashboard stats |
| GET | `/api/analytics/trends` | Workforce trends |
| GET | `/api/analytics/departments` | Dept-wise stats |
| GET | `/api/analytics/salary` | Salary analysis |
| GET | `/api/analytics/attrition` | Attrition insights |

### 🔮 Predictions
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/predict/hiring` | Predict hiring demand |
| POST | `/api/predict/attrition` | Predict attrition risk |

### 🎓 Training
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/training/recommend` | Get training recs |
| GET | `/api/training/history/{employee_id}` | Training history |

### 📋 Strategy
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/strategy/generate` | Generate strategy report |
| GET | `/api/strategy/reports` | List all reports |

**📖 Full API docs:** `http://localhost:8000/docs` (Swagger UI)

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- Git
- Google Gemini API Key ([Get here](https://aistudio.google.com/app/apikey))

### 🔧 Backend Setup

```bash
# Navigate to backend
cd backend

# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (Mac/Linux)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Seed sample data
python database/seed_data.py

# Train ML models
python ml/train_hiring_model.py
python ml/train_attrition_model.py

# Run server
uvicorn main:app --reload