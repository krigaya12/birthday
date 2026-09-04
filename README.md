# Birthday Gallery - Image Sharing Platform

A full-featured image sharing gallery with likes, comments, and admin controls.

## Features

### User Features
- 📸 Upload images
- ❤️ Like/Unlike images
- 💬 Comment on images
- 👁️ View all gallery images
- 📱 Responsive design

### Admin Features
- 🔐 Admin authentication (credentials required)
- 🗑️ Delete images
- 🗑️ Delete comments
- 📊 View all uploads
- 👥 Manage user content
- 📈 Admin dashboard

## Tech Stack

**Frontend:**
- React 18
- Tailwind CSS
- Axios for API calls

**Backend:**
- Node.js + Express
- MongoDB for database
- JWT authentication
- Multer for file uploads
- Cloudinary for image storage

**Deployment:**
- Vercel (Frontend)
- Railway/Render (Backend)
- MongoDB Atlas (Database)

## Setup Instructions

### Local Development

1. Clone the repository
```bash
git clone https://github.com/krigaya12/birthday.git
cd birthday
```

2. Install dependencies
```bash
# Backend
cd backend
npm install

# Frontend
cd ../frontend
npm install
```

3. Create `.env` files

**Backend (.env):**
```
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
ADMIN_USERNAME=admin
ADMIN_PASSWORD=your_secure_password
NODE_ENV=development
```

**Frontend (.env):**
```
REACT_APP_API_URL=http://localhost:5000
```

4. Start the application
```bash
# Terminal 1 - Backend
cd backend
npm start

# Terminal 2 - Frontend
cd frontend
npm start
```

## API Endpoints

### Public Endpoints
- `GET /api/images` - Get all images
- `GET /api/images/:id` - Get image details
- `POST /api/comments` - Add comment
- `POST /api/likes` - Add like
- `DELETE /api/likes/:id` - Remove like
- `POST /api/images/upload` - Upload image

### Admin Endpoints (Protected)
- `DELETE /api/images/:id` - Delete image
- `DELETE /api/comments/:id` - Delete comment
- `GET /api/admin/dashboard` - Admin dashboard stats
- `GET /api/admin/all-comments` - View all comments
- `PATCH /api/admin/images/:id` - Edit image details

## Deployment

### Deploy Backend to Railway
```bash
cd backend
npm install -g railway
railway link
railway up
```

### Deploy Frontend to Vercel
```bash
cd frontend
npm install -g vercel
vercel
```

## Admin Access

Login with your admin credentials to access:
- Admin Dashboard
- Delete images and comments
- Manage all uploads
- View analytics

## Database Schema

### Images
```javascript
{
  _id: ObjectId,
  title: String,
  description: String,
  imageUrl: String,
  uploadedBy: String,
  uploadedAt: Date,
  likes: [userId],
  comments: [commentId]
}
```

### Comments
```javascript
{
  _id: ObjectId,
  imageId: ObjectId,
  author: String,
  text: String,
  createdAt: Date
}
```

## License

MIT License
