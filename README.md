# 📚 Laravel Educational Library

Manage an educational library with Laravel 12. Readers can browse and download PDFs according to their permissions, authors can manage their books, and administrators can manage users, categories and author requests.

## ✨ Features

### 🔐 **Role-Based Access Control**
- **Guest**: View books and categories only
- **User**: Read and download books
- **Author**: Create, edit, and manage their own books
- **Admin**: Full system access and control

### 📖 **Book Management**
- Create, edit, and delete books with PDF file uploads
- Categorize books by categories
- Advanced search and filtering functionality
- Read books online with PDF viewer
- Download books (permission-based)
- Author-specific book management

### 🏷️ **Category Management**
- Create and manage book categories
- Admin-only category management
- Category-based book organization and filtering

### 👥 **User Management**
- User registration and authentication
- Role-based access control
- Admin user management panel
- Profile editing with role management
- Password reset functionality

### 🎨 **Modern UI/UX Design**
- **Dark Mode Support** 🌙
- Responsive design for all devices
- Glassmorphism effects and modern styling
- Smooth animations and transitions
- Modern card-based layouts
- Bootstrap 5 integration

### 📊 **Admin Dashboard**
- Statistics overview
- User management interface
- Book management tools
- Category management
- Author request management
- Notification system

### 🔍 **Advanced Search & Filtering**
- Search books by title, author, description
- Filter by categories
- Real-time search results
- Advanced search interface
- Sort by newest/oldest

## 🚀 Quick Start

### Prerequisites
- PHP 8.2+
- Composer
- MySQL/PostgreSQL
- Node.js & NPM

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/elgiar22/laravel-educational-library.git
cd laravel-educational-library
```

2. **Install dependencies**
```bash
composer install
npm install
```

3. **Environment setup**
```bash
cp .env.example .env
php artisan key:generate
```

4. **Configure database**
Edit `.env` file with your database credentials:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_educational_library
DB_USERNAME=your_database_user
DB_PASSWORD=your_database_password
```

5. **Run migrations**
```bash
php artisan migrate
```

To populate a local demo database, use `php artisan db:seed`. Run `php artisan storage:link` to serve files from the public storage disk.

6. **Build assets**
```bash
npm run build
```

7. **Start the server**
```bash
php artisan serve
```

Visit `http://localhost:8000` to see your application!

## Local demo accounts

The [database seeders](database/seeders/) define sample accounts for testing the local application. Use their demo credentials only in a disposable development database. Create separate accounts with unique passwords for deployed environments.

## 🛠️ Technology Stack

- **Backend**: Laravel 12
- **Frontend**: Blade Templates, Bootstrap 5
- **Database**: MySQL with Eloquent ORM
- **Authentication**: Custom authentication system with password reset
- **File Storage**: Laravel Storage with security validation
- **Styling**: Custom CSS with CSS variables
- **JavaScript**: Vanilla JavaScript for interactions
- **PDF Handling**: Browser-based PDF viewer
- **Security**: Role middleware, input validation, security headers and event logging
- **Rate Limiting**: Multi-level rate limiting system
- **Notifications**: Laravel notification system

## 🔒 Security Features

- Role and ownership checks for protected operations
- Password hashing and token-based password reset
- HTTP security headers and request rate limiting
- File type and size validation for uploads
- Logging for selected authentication and authorization events

See the [backend analysis](BACKEND_ANALYSIS_REPORT.md) for implementation details and open security recommendations.

## 📁 Project Structure

```
laravel-educational-library/
├── app/
│   ├── Http/Controllers/
│   │   ├── AdminController.php      # Admin dashboard and user management
│   │   ├── AuthController.php      # Authentication and password reset
│   │   ├── BookController.php      # Book CRUD operations
│   │   ├── CategoryController.php  # Category management
│   │   ├── HomeController.php      # Home page controller
│   │   └── UserController.php      # User management
│   ├── Http/Middleware/
│   │   ├── CheckPermission.php     # Custom permission middleware
│   │   ├── isAdmin.php            # Admin role middleware
│   │   ├── isAuthor.php           # Author role middleware
│   │   └── SecurityHeaders.php    # Security headers middleware
│   ├── Models/
│   │   ├── Book.php                # Book model with relationships
│   │   ├── Category.php            # Category model
│   │   └── User.php                # User model with roles
│   └── Notifications/
│       ├── AuthorRequestNotification.php
│       └── CustomResetPasswordNotification.php
├── resources/views/
│   ├── Admin/
│   │   ├── dashboard.blade.php     # Admin dashboard
│   │   └── editUser.blade.php      # User editing interface
│   ├── Books/
│   │   ├── all.blade.php           # All books listing
│   │   ├── create.blade.php        # Book creation form
│   │   ├── edit.blade.php          # Book editing form
│   │   ├── mybooks.blade.php       # Author's books
│   │   └── show.blade.php          # Book details view
│   ├── Categories/
│   │   ├── all.blade.php           # All categories listing
│   │   ├── create.blade.php        # Category creation form
│   │   ├── edit.blade.php          # Category editing form
│   │   └── show.blade.php          # Category details view
│   ├── auth/
│   │   ├── login.blade.php         # Login form
│   │   ├── register.blade.php      # Registration form
│   │   ├── forgot-password.blade.php # Password reset request
│   │   └── reset-password.blade.php # Password reset form
│   ├── components/                 # Reusable Blade components
│   ├── layout.blade.php            # Main layout template
│   ├── home.blade.php              # Home page
│   ├── search.blade.php            # Search interface
│   └── welcome.blade.php           # Welcome page
├── public/
│   ├── css/
│   │   ├── style.css               # Main stylesheet
│   │   ├── advanced.css            # Advanced styling
│   │   └── shared.css              # Shared styles
│   ├── js/
│   │   ├── script.js               # Main JavaScript
│   │   └── bootstrap.min.js        # Bootstrap JavaScript
│   └── storage/                    # File storage
├── database/
│   ├── migrations/                 # Database migrations
│   ├── seeders/                    # Database seeders
│   └── factories/                  # Model factories
└── tests/
    ├── Feature/                    # Feature tests
    └── Unit/                       # Unit tests
```

## 🔧 Key Features Implementation

### **Roles & Permissions System**
- Custom middleware for permission checking
- Role-based route protection
- Dynamic permission checking in views
- Flexible permission system with granular control
- Author request system for role elevation

### **File Management**
- Secure PDF file uploads with validation
- File storage configuration with public disk
- Download protection based on user permissions
- Browser-based PDF viewer for reading
- File path management and security

### **Search & Filtering**
- Advanced search functionality across multiple fields
- Category-based filtering
- Real-time search results
- Responsive search interface
- Sort by newest/oldest functionality

### **UI/UX Design**
- CSS Variables for theming
- Dark mode toggle with persistent preference
- Responsive grid layouts
- Modern animations and transitions
- Glassmorphism effects
- Mobile-first design approach
- Bootstrap 5 integration

### **Security Implementation**
- Comprehensive security logging
- Multi-level rate limiting (6/min auth, 3/min author requests, 10/min admin)
- Security headers middleware
- Custom password reset notifications

## 🚀 Web Routes

### Authentication
- `GET /register` - Registration form
- `POST /register` - User registration
- `GET /login` - Login form
- `POST /login` - User login
- `POST /logout` - User logout
- `GET /forgot-password` - Password reset request form
- `POST /forgot-password` - Send password reset email
- `GET /reset-password/{token}` - Password reset form
- `POST /reset-password` - Reset password

### Books
- `GET /Books` - View all books
- `GET /Books/show/{id}` - View book details
- `GET /Books/create` - Create book form (Author/Admin)
- `POST /Books` - Store new book (Author/Admin)
- `GET /Books/edit/{id}` - Edit book form (Author/Admin)
- `PUT /Books/update/{id}` - Update book (Author/Admin)
- `DELETE /Books/{id}` - Delete book (Author/Admin)
- `GET /Books/mybooks` - Author's books (Author)
- `GET /books/read/{book}` - Read book (User+)
- `GET /books/download/{book}` - Download book (User+)

### Categories
- `GET /categories` - View all categories
- `GET /categories/show/{id}` - View category details
- `GET /categories/create` - Create category form (Admin)
- `POST /categories` - Store new category (Admin)
- `GET /categories/edit/{id}` - Edit category form (Admin)
- `PUT /categories/update/{id}` - Update category (Admin)
- `DELETE /categories/{id}` - Delete category (Admin)

### Admin
- `GET /admin/dashboard` - Admin dashboard
- `GET /users/edit/{user}` - Edit user form
- `PUT /users/update/{user}` - Update user
- `DELETE /users/{user}` - Delete user

### Search
- `GET /search` - Search books

## 🧪 Testing

```bash
php artisan test
```

## 🔧 Troubleshooting

### Image Display Issues
If images are not displaying properly:

1. **Create storage symbolic link**:
   ```bash
   php artisan storage:link
   ```

2. **Verify storage configuration**:
   - Ensure `FILESYSTEM_DISK=public` in `.env`
   - Check that `storage/app/public` directory exists
   - Verify symbolic link from `public/storage` to `storage/app/public`

3. **Manual symbolic link creation** (Windows):
   ```cmd
   mklink /D "public\storage" "storage\app\public"
   ```

4. **Check file permissions**:
   - Ensure web server has read access to `storage/app/public`
   - Verify uploaded files are in correct directories

## 📝 Recent Updates

- **Fixed image storage issue**: Updated controllers to use `Storage::disk('public')` for proper file storage
- **Enhanced security**: Improved file upload validation and storage configuration
- **Improved documentation**: Added troubleshooting section for common issues
