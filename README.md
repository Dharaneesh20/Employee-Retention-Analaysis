# Employee Retention Prediction System

A comprehensive web application for predicting employee retention using Machine Learning. Built with Flask, HTML/CSS/JavaScript, and featuring user authentication, data visualization, and real-time predictions.

## Features

### 🔐 User Authentication
- Secure user registration and login
- Password encryption using bcrypt
- Session management
- User-specific model storage

### 📊 Data Analysis
- Interactive data visualizations
- Employee satisfaction analysis
- Department-wise attrition rates
- Salary vs retention correlation
- Key insights and recommendations

### 🧠 Machine Learning
- Random Forest Classifier model
- Automated data preprocessing
- Feature encoding and scaling
- Model training with 80/20 split
- Real-time accuracy reporting

### 🔮 Predictions
- Individual employee prediction
- Probability scores for staying/leaving
- Risk assessment (Low/Medium/High)
- Actionable recommendations
- Interactive prediction form

### 📁 Data Management
- CSV file upload with validation
- Drag & drop interface
- File size and format validation
- Sample dataset included
- Data privacy and security

### 📱 Responsive Design
- Modern Bootstrap 5 interface
- Mobile-friendly design
- Interactive animations
- Professional UI/UX
- Dark/light theme support

## Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup Instructions

1. **Clone or download the project files**
   ```bash
   cd aiml_g
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   # source venv/bin/activate  # On macOS/Linux
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize the database**
   ```bash
   python -c "from app import app, db; app.app_context().push(); db.create_all()"
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

6. **Access the application**
   Open your browser and navigate to `http://localhost:5000`

## Usage Guide

### 1. Registration & Login
- Create a new account with username, email, and password
- Login with your credentials
- Access the personalized dashboard

### 2. Upload Employee Data
- Navigate to "Upload Data" section
- Upload a CSV file with employee information
- Required columns:
  - `satisfaction_level` (0.0-1.0)
  - `last_evaluation` (0.0-1.0)
  - `number_project` (integer)
  - `average_montly_hours` (integer)
  - `time_spend_company` (years)
  - `Work_accident` (0 or 1)
  - `left` (0=stayed, 1=left)
  - `promotion_last_5years` (0 or 1)
  - `Department` (string)
  - `salary` (low/medium/high)

### 3. Analyze Data
- View interactive visualizations
- Understand employee satisfaction patterns
- Analyze attrition by department and salary
- Get actionable insights

### 4. Train ML Model
- Automatically preprocess your data
- Train Random Forest model
- View model accuracy and performance
- Save trained model for predictions

### 5. Make Predictions
- Enter individual employee details
- Get probability scores for retention
- Receive risk assessment
- Get personalized recommendations

## Project Structure

```
aiml_g/
├── app.py                 # Main Flask application
├── config.py             # Configuration settings
├── requirements.txt      # Python dependencies
├── README.md            # Project documentation
├── data/                # Sample datasets
│   └── HR_comma_sep.csv
├── templates/           # HTML templates
│   ├── base.html
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── data_analysis.html
│   ├── train_model.html
│   ├── predict.html
│   └── upload_data.html
├── static/              # Static assets
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── main.js
├── models/              # Trained ML models (created automatically)
├── uploads/             # Uploaded files (created automatically)
└── instance/            # Database files (created automatically)
```

## Technology Stack

### Backend
- **Flask** - Web framework
- **SQLAlchemy** - Database ORM
- **Flask-Bcrypt** - Password hashing
- **scikit-learn** - Machine learning
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **matplotlib** - Data visualization
- **seaborn** - Statistical visualization

### Frontend
- **HTML5** - Markup
- **CSS3** - Styling
- **JavaScript** - Interactivity
- **Bootstrap 5** - CSS framework
- **Font Awesome** - Icons

### Database
- **SQLite** - Development database
- **PostgreSQL** - Production ready (configurable)

## Model Details

### Algorithm
- **Random Forest Classifier** with 100 estimators
- **Max depth**: 10
- **Min samples split**: 5
- **Random state**: 42 for reproducibility

### Features Used
1. Satisfaction Level (0.0-1.0)
2. Last Evaluation Score (0.0-1.0)
3. Number of Projects (integer)
4. Average Monthly Hours (integer)
5. Time with Company (years)
6. Work Accidents (binary)
7. Recent Promotions (binary)
8. Department (encoded)
9. Salary Level (encoded)

### Performance
- **Typical Accuracy**: 85-95%
- **Training/Test Split**: 80/20
- **Cross Validation**: Stratified split
- **Preprocessing**: Feature scaling and encoding

## Security Features

- Password hashing with bcrypt
- Session management
- CSRF protection ready
- File upload validation
- SQL injection prevention
- XSS protection

## Configuration

### Environment Variables
Create a `.env` file for customization:

```env
SECRET_KEY=your-secret-key-here
DATABASE_URL=sqlite:///employee_retention.db
UPLOAD_FOLDER=uploads
MODEL_FOLDER=models
FLASK_DEBUG=False
```

### Production Deployment
For production deployment:

1. Set `FLASK_DEBUG=False`
2. Use a strong `SECRET_KEY`
3. Configure a production database (PostgreSQL)
4. Set up proper file permissions
5. Use a WSGI server (Gunicorn, uWSGI)
6. Configure reverse proxy (Nginx)

## Sample Data

The application includes a sample HR dataset with 82 employee records. You can also download larger datasets from:
- [Kaggle HR Analytics Dataset](https://www.kaggle.com/datasets/liujiaqi/hr-comma-sepcsv)
- Create your own CSV following the required format

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For questions or issues:
1. Check the documentation
2. Review the sample data format
3. Ensure all dependencies are installed
4. Check the console for error messages

## Acknowledgments

- Bootstrap team for the excellent CSS framework
- Font Awesome for the icon library
- scikit-learn team for machine learning tools
- Flask community for the web framework

---

**Built with ❤️ for HR professionals and data scientists**