# FinCheck AI - Peer-to-Peer (P2P) Lending Intelligence Platform

FinCheck AI is a modern, full-stack, AI-powered Peer-to-Peer (P2P) Lending Intelligence Platform. It enables Borrowers (Vendors) to submit loan requests and build credit trust scores through document verification, while Lenders register their investment preferences to receive optimized, dual-acceptance borrower-lender match recommendations.

---

## 🚀 Key Features

1. **AI Underwriting & Risk Engine**:
   - Analyzes applicant financial metrics (Income, DTI, existing EMIs, guarantor capacity) using a Scikit-Learn `RandomForestClassifier`.
   - Explains decisions (XAI) using custom positive/negative factor checklists.
2. **KYC & Trust Score Progress Tracker**:
   - Calculates a custom Trust Score (0–100) mapped to four levels (**Bronze**, **Silver**, **Gold**, **Platinum**).
   - Dynamic document verification upload slot (PAN, Aadhaar, Bank Statement, Salary Slips, and Business Registration) with a circular progress gauge.
3. **P2P Compatibility Matching Engine**:
   - Matches lenders and borrowers based on location, capital thresholds, tenure, and trust requirements.
   - Dual-acceptance workflow: Contact details are strictly locked until both parties click "Accept Match".
4. **Lender administration dashboard**:
   - Aggregate queue counts and stats (Approved, Rejected, Pending).
   - Rich interactive Chart.js analytics representing approval ratios, submission trends, and risk distributions.
5. **Interactive EMI Calculator**:
   - Supports live numeric input fields (e.g. ₹102,000) and sliding controls with payment breakdown tables.
6. **AI Assistant chatbot**:
   - Floating chat panel offering automated financial guidance and underwriting tips.

---

## 📁 Directory Structure

```text
fincheck/
├── backend/
│   ├── app.py                # Flask application & API routes
│   ├── database.py           # SQLite schema and initial database setup
│   ├── train_model.py        # ML training dataset generator and random forest trainer
│   ├── test_app.py           # Core unit testing suite
│   ├── requirements.txt      # Python dependencies
│   └── data/
│       └── sample_loans.csv  # Synthesized training loans data
└── frontend/
    ├── static/
    │   ├── css/
    │   │   └── styles.css    # Premium glassmorphic design stylesheet
    │   └── js/
    │       ├── main.js       # Core navigation and forms validation
    │       ├── charts.js     # Chart.js analytics loaders
    │       └── calculator.js # Live EMI payment logic
    └── templates/
        ├── base.html         # Main dashboard layout wrapper & chatbot
        ├── landing.html      # Public home portal & features
        ├── login.html        # Registration & authentication forms
        ├── apply.html        # Multi-step loan request wizard
        ├── result.html       # Underwriting findings & parameter checks
        ├── dashboard_applicant.html # Borrower panel (KYC, Chat, match states)
        ├── dashboard_lender.html    # Lender preferences & match actions
        ├── dashboard_admin.html     # Administration queue & metrics charts
        └── calculator.html   # Standalone EMI widget
```

---

## 🛠️ Installation & Setup

### 1. Install Dependencies
Navigate into the `backend` directory and install the required libraries:
```bash
cd backend
pip install -r requirements.txt
```

### 2. Train the Machine Learning Model
Generate the synthethic training dataset and fit the StandardScaler / RandomForest model:
```bash
python train_model.py
```
This produces `model.joblib` and `scaler.joblib` in the backend folder.

### 3. Initialize the database
Create the SQLite tables and seed initial mock accounts:
```bash
python database.py
```

### 4. Run the Application
Launch the Flask development server:
```bash
python app.py
```
Open **`http://127.0.0.1:5000`** in your browser.

---

## 🧪 Testing Accounts

| Role | Username | Password |
| :--- | :--- | :--- |
| **Lender / Admin** | `lender` | `lender123` |
| **Borrower** | `user` | `user123` |
| **System Admin** | `admin` | `admin123` |
