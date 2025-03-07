# **📧 Spam Email Classifier**  
*A full-stack Django-based spam classifier using Naive Bayes and Word2Vec*  

![Spam Classifier Banner](https://www.linktoimage.com/spam_classifier.png) *(Replace with an actual image if available)*  

---

## **📌 Overview**  
This project is a **machine-learning-powered spam email classifier** that allows users to input emails and determine whether they are **Spam** or **Ham** (Not Spam). The system is built with Django, PostgreSQL, and a **Naive Bayes model with Word2Vec for text vectorization**.  

### **✨ Key Features**  
✅ **Email Classification** – Detects whether an email is spam or ham  
✅ **User Feedback System** – Users can correct misclassifications to improve the model  
✅ **API Integration** – Exposes an API for seamless integration with other services  
✅ **Spam Trend Analysis** – Visualizes spam trends using Chart.js  
✅ **Secure Authentication** – Token-based authentication for API usage  
✅ **Scalable & Dockerized** – Fully containerized and production-ready  

---

## **🛠️ Tech Stack**  

| Category            | Technologies Used |
|---------------------|------------------|
| **Backend**        | Django, Django REST Framework |
| **Machine Learning** | Word2Vec, Naive Bayes, Scikit-learn |
| **Frontend**       | HTML, CSS, JavaScript, Chart.js |
| **Database**       | PostgreSQL |
| **Deployment**     | Docker, CI/CD, Gunicorn |

---

## **🚀 Installation & Setup**  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/yourusername/spam-classifier.git
cd spam-classifier
```

### **2️⃣ Set Up a Virtual Environment**  
```bash
python -m venv env
source env/bin/activate   # On Windows use: env\Scripts\activate
```

### **3️⃣ Install Dependencies**  
```bash
pip install -r requirements.txt
```

### **4️⃣ Set Up the Database (PostgreSQL)**  
Modify `settings.py` to match your PostgreSQL credentials:  
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'spam_db',
        'USER': 'your_username',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```
Run database migrations:  
```bash
python manage.py migrate
```

### **5️⃣ Train & Save the Model**  
```bash
python train_model.py
```

### **6️⃣ Run the Server**  
```bash
python manage.py runserver
```
Access the frontend at `http://127.0.0.1:8000/`  
Access the API at `http://127.0.0.1:8000/api/docs/`  

---

## **🖥️ API Endpoints**  

| Method | Endpoint | Description |
|--------|---------|-------------|
| **POST** | `/api/classify/` | Classifies an email as Spam or Ham |
| **POST** | `/api/feedback/` | Allows users to correct a classification |
| **GET** | `/api/trends/` | Returns spam trends as JSON |
| **GET** | `/api/docs/` | API Documentation (Swagger) |

### **Example Classification Request**  
```json
{
    "email_text": "Congratulations! You won a free iPhone!"
}
```
### **Example Response**  
```json
{
    "classification": "Spam",
    "confidence": 0.92
}
```

---

## **📊 Frontend Features**  
- **📩 Email Input** – Users enter emails to classify  
- **📈 Spam Trend Chart** – Displays a graph of spam trends  
- **🛠 User Feedback** – Users can mark emails as incorrectly classified  
- **🔐 Secure Authentication** – Login system for API access  

---

## **🐳 Docker Deployment**  

### **1️⃣ Build the Docker Image**  
```bash
docker build -t spam-classifier .
```

### **2️⃣ Run the Docker Container**  
```bash
docker run -p 8000:8000 spam-classifier
```

### **3️⃣ Access the API**  
Open `http://127.0.0.1:8000/api/docs/` in your browser.  

---

## **🔄 CI/CD Pipeline**  
A **GitHub Actions workflow** automates testing and deployment:  
- ✅ **Runs tests using Pytest**  
- ✅ **Builds and deploys Docker containers**  
- ✅ **Deploys to production if tests pass**  

Example **`.github/workflows/deploy.yml`**:  
```yaml
name: CI/CD Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Build Docker Image
        run: docker build -t spam-classifier .
      
      - name: Run Tests
        run: pytest
```

---

## **📜 License**  
This project is licensed under the **MIT License**.  

---

## **👨‍💻 Contributing**  
Contributions are welcome! Feel free to fork the repo and submit a PR.  

---

## **📞 Contact**  
💬 Have questions? Contact me at **pandeyamartya@outlook.com** or open an issue.  

---

🚀 **Enjoy using the Spam Email Classifier!** 🚀  
