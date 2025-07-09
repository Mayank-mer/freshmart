# 🛒 FreshMart - Grocery Website

A modern, full-stack grocery e-commerce website built with React frontend and Flask backend.

## ✨ Features

### 🛍️ Shopping Experience
- **Product Catalog** with categories (Fruits, Vegetables, Dairy, etc.)
- **Hero Banner** with featured products and deals
- **Category Filtering** for easy product discovery
- **Shopping Cart** with add/remove functionality
- **Checkout Process** with mock payment integration
- **Order History** for users to track purchases

### 👤 User Management
- **User Registration & Login** with JWT authentication
- **User Profiles** and order tracking
- **Secure Password Hashing** with bcrypt

### 🛠️ Admin Panel
- **Product Management** (Add, Edit, Delete products)
- **Order Management** (View all orders across users)
- **Admin-only Access** with role-based permissions

### 🎨 Modern UI/UX
- **Responsive Design** works on desktop and mobile
- **Material UI Components** for consistent design
- **Smooth Animations** with Framer Motion
- **Interactive Elements** with hover effects and transitions

## 🏗️ Tech Stack

### Frontend
- **React 18** with functional components and hooks
- **Material UI** for modern, responsive design
- **Framer Motion** for smooth animations
- **React Router** for navigation
- **Axios** for API communication

### Backend
- **Flask** Python web framework
- **SQLAlchemy** ORM for database management
- **SQLite** database (can be upgraded to PostgreSQL)
- **JWT** for secure authentication
- **Flask-CORS** for cross-origin requests
- **Flask-Bcrypt** for password hashing

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Node.js 16+
- npm or yarn

### 1. Clone the Repository
```bash
git clone <your-repo-url>
cd webd
```

### 2. Backend Setup (Flask)
```bash
cd client/flask_server

# Install Python dependencies
pip install -r requirements.txt

# Initialize database and add sample products
python populate_products.py

# Start the Flask server
python app.py
```

The backend will be available at `http://localhost:5000`

### 3. Frontend Setup (React)
```bash
cd client

# Install Node.js dependencies
npm install

# Start the development server
npm start
```

The frontend will be available at `http://localhost:3000`

### 4. Access the Application
- **Main Website:** `http://localhost:5000` (served by Flask)
- **API Endpoints:** `http://localhost:5000/api/*`
- **Admin Panel:** Available after login as admin user

## 📁 Project Structure

```
webd/
├── client/
│   ├── flask_server/          # Flask backend
│   │   ├── app.py            # Main Flask application
│   │   ├── models.py         # Database models
│   │   ├── populate_products.py  # Sample data script
│   │   ├── requirements.txt  # Python dependencies
│   │   ├── static/           # Static files (React build)
│   │   └── render.yaml       # Render deployment config
│   ├── src/                  # React source code
│   │   ├── components/       # Reusable components
│   │   ├── pages/           # Page components
│   │   ├── App.js           # Main React app
│   │   ├── index.js         # React entry point
│   │   └── api.js           # API configuration
│   ├── public/              # Static assets
│   └── package.json         # Node.js dependencies
└── README.md
```

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login

### Products
- `GET /api/products` - Get all products
- `GET /api/products/<id>` - Get specific product
- `POST /api/products` - Add product (admin only)
- `PUT /api/products/<id>` - Update product (admin only)
- `DELETE /api/products/<id>` - Delete product (admin only)

### Cart
- `GET /api/cart` - Get user's cart
- `POST /api/cart` - Add item to cart
- `DELETE /api/cart/<productId>` - Remove item from cart

### Orders
- `GET /api/orders` - Get user's order history
- `POST /api/orders` - Place new order
- `GET /api/admin/orders` - Get all orders (admin only)

### Payment
- `POST /api/payment` - Mock payment processing

## 🌐 Deployment

### Backend Deployment (Render.com)

1. **Push code to GitHub**
2. **Go to [Render.com](https://render.com/)**
3. **Create New Web Service**
4. **Connect your GitHub repository**
5. **Configure:**
   - **Root Directory:** `client/flask_server`
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn app:app`
6. **Add disk for SQLite persistence**
7. **Deploy and note your URL**

### Frontend Deployment (Vercel)

1. **Go to [Vercel.com](https://vercel.com/)**
2. **Import your GitHub repository**
3. **Configure:**
   - **Root Directory:** `client`
   - **Build Command:** `npm run build`
   - **Output Directory:** `build`
4. **Add Environment Variable:**
   - `REACT_APP_API_URL` = your Render backend URL
5. **Deploy**

### Environment Variables

**Frontend (.env):**
```
REACT_APP_API_URL=https://your-backend.onrender.com
```

**Backend (Render Environment Variables):**
```
JWT_SECRET_KEY=your-secret-key
FLASK_ENV=production
```

## 👥 User Roles

### Regular User
- Browse products
- Add items to cart
- Place orders
- View order history
- Update profile

### Admin User
- All regular user features
- Manage products (CRUD operations)
- View all orders across users
- Access admin panel

## 🛠️ Development

### Adding New Features
1. **Backend:** Add new routes in `app.py`
2. **Frontend:** Create new components in `src/components/`
3. **Database:** Update models in `models.py` if needed

### Database Management
```bash
# Add sample products
python populate_products.py

# Create admin user (via API or database)
# Update user.is_admin = True in database
```

### Styling
- Use Material UI components for consistency
- Add animations with Framer Motion
- Follow the existing design patterns

## 🐛 Troubleshooting

### Common Issues

1. **Port already in use:**
   ```bash
   # Kill process on port 5000
   lsof -ti:5000 | xargs kill -9
   ```

2. **Database issues:**
   ```bash
   # Remove and recreate database
   rm grocery.db
   python app.py  # This will recreate the database
   python populate_products.py
   ```

3. **CORS errors:**
   - Ensure Flask-CORS is properly configured
   - Check API URL in frontend environment variables

4. **Build errors:**
   ```bash
   # Clear npm cache
   npm cache clean --force
   rm -rf node_modules package-lock.json
   npm install
   ```

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

For questions or issues:
- Create an issue in the GitHub repository
- Check the troubleshooting section above
- Review the API documentation

---

**Happy Shopping! 🛒✨** 