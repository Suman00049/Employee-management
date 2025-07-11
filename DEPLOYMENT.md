# Vercel Deployment Guide 2025

This guide will help you deploy the Employee Attendance Dashboard to Vercel with separate frontend and backend deployments.

## 📋 Prerequisites

1. **Vercel Account**: Sign up at [vercel.com](https://vercel.com)
2. **GitHub Repository**: Push your code to GitHub
3. **MongoDB Atlas**: Set up a MongoDB database
4. **Firebase Project**: Configure Firebase Authentication

## 🚀 Deployment Steps

### 1. Backend Deployment

1. **Create New Project in Vercel**
   - Go to Vercel Dashboard
   - Click "New Project"
   - Import your GitHub repository
   - Select the `backend` folder as the root directory

2. **Configure Environment Variables**
   ```
   NODE_ENV=production
   PORT=3001
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/attendance?retryWrites=true&w=majority
   FRONTEND_URL=https://your-frontend-app.vercel.app
   ```

3. **Deploy Backend**
   - Click "Deploy"
   - Note the deployment URL (e.g., `https://your-backend-app.vercel.app`)

### 2. Frontend Deployment

1. **Create Another New Project in Vercel**
   - Import the same GitHub repository
   - Select the root directory (not backend folder)

2. **Configure Environment Variables**
   ```
   VITE_API_URL=https://your-backend-app.vercel.app
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
   VITE_FIREBASE_PROJECT_ID=your_project_id
   VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
   VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
   VITE_FIREBASE_APP_ID=your_app_id
   VITE_FIREBASE_MEASUREMENT_ID=your_measurement_id
   ```

3. **Deploy Frontend**
   - Click "Deploy"
   - Your frontend will be available at `https://your-frontend-app.vercel.app`

### 3. Update Backend CORS

After frontend deployment, update the backend environment variables:
```
FRONTEND_URL=https://your-actual-frontend-url.vercel.app
```

## 🔧 Configuration Files

The project includes these deployment-ready files:

- **Frontend**: `vercel.json` - Handles SPA routing
- **Backend**: `backend/vercel.json` - Node.js serverless configuration
- **Environment**: `.env.example` files for both frontend and backend

## 🧪 Testing Deployment

1. **Health Check**: Visit `https://your-backend-app.vercel.app/health`
2. **Frontend**: Visit `https://your-frontend-app.vercel.app`
3. **Demo Accounts**: 
   - Employee: `employee@demo.com` / `password123`
   - Admin: `admin@demo.com` / `admin123`

## 🔒 Security Checklist

- ✅ Environment variables configured
- ✅ CORS properly set up
- ✅ Firebase authentication enabled
- ✅ MongoDB connection secured
- ✅ API endpoints protected

## 🐛 Troubleshooting

### Common Issues:

1. **CORS Errors**: Ensure `FRONTEND_URL` is set correctly in backend
2. **Firebase Errors**: Verify all Firebase environment variables
3. **Database Connection**: Check MongoDB URI and network access
4. **API Not Found**: Ensure backend is deployed and URL is correct

### Debug Steps:

1. Check Vercel function logs
2. Verify environment variables
3. Test API endpoints directly
4. Check browser network tab for errors

## 📱 Features Working in Production

- ✅ User authentication (Firebase)
- ✅ Employee dashboard with clock in/out
- ✅ Break tracking (lunch/snack)
- ✅ Admin dashboard with reports
- ✅ CSV export functionality
- ✅ Real-time attendance tracking
- ✅ Responsive design for mobile/desktop

## 🔄 Continuous Deployment

Both frontend and backend will automatically redeploy when you push changes to your GitHub repository.

## 📞 Support

If you encounter issues:
1. Check Vercel deployment logs
2. Verify all environment variables
3. Test locally first
4. Check Firebase and MongoDB configurations

Your Employee Attendance Dashboard is now ready for production use in 2025! 🎉