# Railway-Navigation-project

# Railway Station Navigation Web App

A full-stack web application that helps users navigate inside large railway stations with interactive maps, real-time announcements, and comprehensive facility management.

## 🌟 Features

### 👤 User Features
- **User Registration/Login** - Secure authentication with JWT tokens
- **Interactive Station Map** - Clickable floor plan with facility markers
- **Smart Search** - Find facilities, platforms, and locations quickly
- **Live Announcements** - Real-time updates on delays, platform changes, etc.
- **Accessibility Support** - Filter for accessible facilities (lifts, ramps, etc.)
- **Feedback System** - Report issues and provide feedback
- **Navigation Directions** - Step-by-step directions between facilities

### 🔧 Admin Features
- **Facility Management** - Add, edit, and delete station facilities
- **Announcement System** - Create and manage real-time announcements
- **Feedback Management** - View and respond to user feedback
- **Dashboard Analytics** - Overview of system usage and statistics

## 🛠️ Tech Stack

### Frontend
- **React.js** - Modern UI framework
- **Tailwind CSS** - Utility-first CSS framework
- **React Router** - Client-side routing
- **Socket.IO Client** - Real-time communication
- **Framer Motion** - Smooth animations
- **React Icons** - Icon library
- **Axios** - HTTP client

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **MySQL** - Relational database
- **Socket.IO** - Real-time bidirectional communication
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **Helmet** - Security middleware

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Node.js** (v14 or higher)
- **MySQL** (v8.0 or higher)
- **npm** or **yarn**

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd railway-station-navigation
```

### 2. Install Dependencies
```bash
# Install root dependencies
npm install

# Install server dependencies
cd server
npm install

# Install client dependencies
cd ../client
npm install
```

### 3. Database Setup

#### Create MySQL Database
```sql
CREATE DATABASE railway_navigation;
```

#### Configure Environment Variables
Copy the example environment file and configure your database settings:

```bash
cd server
cp env.example .env
```

Edit the `.env` file with your database credentials:
```env
# Database Configuration
DB_HOST=localhost
DB_USER=your_username
DB_PASSWORD=your_password
DB_NAME=railway_navigation

# JWT Configuration
JWT_SECRET=your-super-secret-jwt-key-change-this-in-production

# Session Configuration
SESSION_SECRET=your-session-secret-key-change-this-in-production

# Server Configuration
PORT=5000
NODE_ENV=development

# CORS Configuration
CORS_ORIGIN=http://localhost:3000
```

### 4. Initialize Database
The application will automatically create tables and insert sample data when you first run the server.

### 5. Start the Application

#### Development Mode (Recommended)
```bash
# From the root directory
npm run dev
```

This will start both the backend server (port 5000) and frontend development server (port 3000) concurrently.

#### Manual Start
```bash
# Start backend server
cd server
npm run dev

# In a new terminal, start frontend
cd client
npm start
```

### 6. Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000

## 🔐 Default Admin Account

The application creates a default admin account during database initialization:

- **Username**: admin
- **Password**: admin123
- **Email**: admin@railway.com

**⚠️ Important**: Change these credentials in production!

## 📁 Project Structure

```
railway-station-navigation/
├── client/                 # React frontend
│   ├── public/            # Static files
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── contexts/      # React contexts
│   │   ├── pages/         # Page components
│   │   └── ...
│   └── package.json
├── server/                # Node.js backend
│   ├── config/           # Database configuration
│   ├── routes/           # API routes
│   ├── middleware/       # Custom middleware
│   └── ...
├── package.json          # Root package.json
└── README.md
```

## 🗄️ Database Schema

### Users Table
- User authentication and role management
- Supports both regular users and admins

### Facilities Table
- Station facilities with coordinates and metadata
- Supports accessibility features

### Announcements Table
- Real-time announcements with priority levels
- Tracks creation and modification

### Feedback Table
- User feedback and issue reports
- Status tracking for admin management

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `POST /api/auth/logout` - User logout

### Facilities
- `GET /api/facilities` - Get all facilities
- `GET /api/facilities/:id` - Get specific facility
- `GET /api/facilities/search/:query` - Search facilities
- `GET /api/facilities/navigation/:fromId/:toId` - Get navigation path

### Announcements
- `GET /api/announcements` - Get active announcements
- `POST /api/announcements` - Create announcement (admin)
- `PUT /api/announcements/:id` - Update announcement (admin)
- `DELETE /api/announcements/:id` - Delete announcement (admin)

### Feedback
- `POST /api/feedback` - Submit feedback
- `GET /api/feedback` - Get all feedback (admin)
- `PUT /api/feedback/:id/status` - Update feedback status (admin)

### Admin
- `GET /api/admin/dashboard/stats` - Dashboard statistics
- `POST /api/admin/facilities` - Create facility
- `PUT /api/admin/facilities/:id` - Update facility
- `DELETE /api/admin/facilities/:id` - Delete facility

## 🎨 Customization

### Adding New Facility Types
1. Update the database enum in `server/config/database.js`
2. Add corresponding icons in the frontend
3. Update the facility management components

### Styling
The application uses Tailwind CSS. Custom styles can be added in:
- `client/src/index.css` - Global styles
- `client/tailwind.config.js` - Tailwind configuration

### Real-time Features
Socket.IO is used for real-time announcements. Additional real-time features can be added by:
1. Emitting events from the server
2. Listening to events in the frontend Socket context

## 🚀 Deployment

### Frontend Deployment
```bash
cd client
npm run build
```

The build folder can be deployed to any static hosting service.

### Backend Deployment
1. Set up a production MySQL database
2. Configure environment variables for production
3. Use a process manager like PM2:
```bash
npm install -g pm2
pm2 start server/index.js --name "railway-navigation"
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Contact the development team

## 🔄 Updates

Stay updated with the latest features and improvements by regularly pulling from the main branch.

---

**Happy Navigating! 🚂✨** 
