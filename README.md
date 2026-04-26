# 📧 MemoIt - Memo Mailing Application

<div align="center">
  <p><strong>A secure desktop application for composing, managing, and sending memos to employees with integrated email functionality</strong></p>
</div>

---

## 📋 Overview

**MemoIt** is a user-friendly desktop application designed for organizations to efficiently compose and send memos to employees. The application features password-protected access, employee database management, and integrated email capabilities to streamline internal communications.

## ✨ Key Features

- **🔐 Secure Access**: Password-protected login system for authorized personnel
- **📧 Email Integration**: Send memos directly via email with subject and body content
- **👥 Employee Management**: Add and manage employee records with ID, name, and email
- **💾 Database Storage**: Persistent storage of employee information using database connectivity
- **🎨 Intuitive GUI**: User-friendly Tkinter interface with logo branding
- **📝 Multi-Page Navigation**: Seamless navigation between different application modules
- **🔄 Session Management**: Login/Logout functionality

## 🛠️ Technology Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Python 3 |
| **GUI Framework** | Tkinter |
| **Database** | MySQL/Database Connection Module |
| **Email Service** | SMTP Integration |
| **Image Processing** | Pillow (PIL) |

## 📦 Core Modules

### Main Components

| Module | Purpose |
|--------|---------|
| **MainApp.py** | Application entry point with frame management |
| **Pages.py** | Multi-page UI implementation (6 different pages) |
| **databaseconnection.py** | Database connectivity and employee management |
| **emailsenderapp.py** | Email sending functionality |

### UI Pages

1. **StartPage**: Password authentication screen
2. **PageOne**: Main menu (Send Memo, Add Employee, Logout)
3. **WrongPasswordPage**: Error handling for incorrect passwords
4. **PageTwo**: Employee selection dropdown
5. **PageThree**: Add new employee form
6. **PageFour**: Memo composition interface

## 🚀 Getting Started

### Prerequisites

- Python 3.6+
- MySQL Database
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ayushi200116/MemoIt-Memo-Mailing-application.git
   cd MemoIt-Memo-Mailing-application
   ```

2. **Install dependencies**
   ```bash
   pip install pillow
   ```

3. **Configure Database**
   - Update database connection details in `databaseconnection.py`
   - Ensure MySQL database is running

4. **Set up Password**
   - Configure password in `Passwords.txt`

### Running the Application

```bash
python MainApp.py
```

## 📁 Project Structure

```
MemoIt-Memo-Mailing-application/
├── MainApp.py                  # Application entry point
├── Pages.py                    # UI page definitions
├── databaseconnection.py        # Database operations
├── emailsenderapp.py            # Email functionality
├── PageLogo.png                 # Small application logo
├── PageLogoLarge.png            # Large memo composition logo
├── Passwords.txt                # Password storage
└── README.md
```

## 🔧 Configuration

### Database Setup

Edit `databaseconnection.py` with your database credentials:

```python
# Database connection parameters
host = "localhost"
user = "root"
password = "your_password"
database = "your_database"
```

### Password Configuration

Update `Passwords.txt` with your desired password.

### Email Configuration

Configure SMTP settings in `emailsenderapp.py`:

```python
# Email service credentials
sender_email = "your_email@gmail.com"
sender_password = "your_app_password"
smtp_server = "smtp.gmail.com"
smtp_port = 587
```

## 📊 Application Workflow

```
Start Application
      ↓
Enter Password → Authenticate
      ↓
Main Menu
  ├─ Send Memo
  │    ├─ Select Employee
  │    └─ Compose & Send Email
  ├─ Add Employee
  │    ├─ Enter ID, Name, Email
  │    └─ Save to Database
  └─ Logout → Return to Login
```

## 🎯 Use Cases

- **HR Communications**: Send policy updates and announcements
- **Management Memos**: Distribute important notices to staff
- **Meeting Reminders**: Schedule and send meeting notifications
- **Employee Onboarding**: Add new employees to the system
- **Internal Messaging**: Secure inter-departmental communication

## 📋 Database Schema

**Employees Table Example:**
```
ID    | Name          | Email              | Department
------|---------------|--------------------|-----------
E001  | John Doe      | john@company.com   | IT
E002  | Jane Smith    | jane@company.com   | HR
```

## ⚠️ Important Notes

- Ensure MySQL database is running before launching the application
- Store credentials securely, do not commit sensitive data
- Use app-specific passwords for email accounts
- Regularly backup employee database

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| Database Connection Error | Verify MySQL is running and credentials are correct |
| Email Not Sending | Check SMTP settings and verify app password |
| GUI Not Displaying | Ensure Tkinter and Pillow are properly installed |
| Image Not Loading | Verify PageLogo.png and PageLogoLarge.png exist in root directory |

## 📝 License

This project is provided as-is for educational and organizational use.

## 🤝 Contributing

Contributions and improvements are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

---

<div align="center">
  <p>Built to streamline internal communications ❤️</p>
</div>
