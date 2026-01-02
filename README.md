# Government of Jharkhand Complaint Management System

A web application for citizens to submit and track complaints related to government services in Jharkhand, India. The system includes user authentication, complaint filing with file uploads, and an admin dashboard for managing complaints.

## Features

- **User Registration and Authentication**: Secure login system using Passport.js
- **Complaint Submission**: Users can file complaints with descriptions, categories, and file attachments
- **Complaint Tracking**: Users can view and track the status of their submitted complaints
- **Admin Dashboard**: Administrators can view, categorize, and manage all complaints
- **File Uploads**: Support for uploading images/documents with complaints
- **Email Notifications**: Automated email notifications for complaint updates
- **Responsive Design**: Mobile-friendly interface using EJS templates

## Technologies Used

- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: Passport.js with Local Strategy
- **Templating**: EJS with EJS-Mate
- **File Uploads**: Multer
- **Email**: Nodemailer
- **Session Management**: Express-Session
- **Password Hashing**: bcrypt
- **Flash Messages**: connect-flash

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Abudarda12/Government-of-Jharkhand.git
   cd Government-of-Jharkhand
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up environment variables**:
   Create a `.env` file in the root directory with the following variables:
   ```
   MONGO_URI=your_mongodb_connection_string
   PORT=3000
   SESSION_SECRET=your_session_secret
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASS=your_email_password
   ```

4. **Seed admin user** (optional):
   ```bash
   node seedAdmin.js
   ```

## Usage

1. **Start the server**:
   ```bash
   node app.js
   ```

2. **Open your browser** and navigate to `http://localhost:3000`

3. **Register/Login** as a user to submit complaints

4. **Admin access**: Use the seeded admin credentials to access the admin dashboard

## Project Structure

```
├── app.js                 # Main application file
├── seedAdmin.js           # Admin user seeding script
├── config/
│   └── passport.js        # Passport authentication configuration
├── models/
│   ├── Complaint.js       # Complaint model
│   └── User.js           # User model
├── routes/
│   ├── auth.js           # Authentication routes
│   ├── complaintRoutes.js # Complaint management routes
│   └── dashboardRoutes.js # Dashboard routes
├── views/                # EJS templates
│   ├── index.ejs
│   ├── login.ejs
│   ├── register.ejs
│   ├── userDashboard.ejs
│   ├── newComplaints.ejs
│   └── admin/
│       ├── dashboard.ejs
│       └── dashboards/
│           ├── electricity.ejs
│           ├── roads.ejs
│           ├── sanitation.ejs
│           └── water.ejs
├── public/               # Static files (CSS, JS)
├── uploads/              # File uploads directory
└── utils/
    ├── authGuard.js      # Authentication middleware
    └── sendEmail.js      # Email utility
```

## API Endpoints

### Authentication
- `GET /` - Home page
- `GET /login` - Login page
- `POST /login` - Login user
- `GET /register` - Registration page
- `POST /register` - Register new user
- `GET /logout` - Logout user

### Complaints
- `GET /complaints/new` - New complaint form
- `POST /complaints` - Submit new complaint
- `GET /complaints/:id` - View specific complaint
- `GET /dashboard` - User dashboard

### Admin
- `GET /admin/login` - Admin login
- `POST /admin/login` - Admin login
- `GET /admin/dashboard` - Admin dashboard
- `GET /admin/dashboard/:category` - Category-specific dashboard

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License.

## Contact

For questions or support, please contact the me.