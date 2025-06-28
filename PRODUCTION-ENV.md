# Production Environment Configuration for Deployment

## Backend Environment Variables (for Render.com Web Service)

```
DATABASE_URL=postgresql://root:39CJQ67WEA2GJ9MWmrB2iMh0xHfkL013@dpg-d1b9ktmuk2gs739h3abg-a.singapore-postgres.render.com/new1_yk9v
JWT_SECRET=MysecretKey@Phrase!
NODE_ENV=production
PORT=10000

# API Keys
GEMINI_API_KEY=AIzaSyAY42lqkStH_iuglzwL_8OZAMVWoV1PY2c
OPENWEATHER_API_KEY=a5f2bbf9e0cd0082dc1dd6c267ee1b5b
GOOGLE_MAPS_API_KEY=AIzaSyAONqru6YbrCzb6ZlSROmvBGeyD-6TvXPo

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=tmkoc6465@gmail.com
EMAIL_PASS=htxiwcpohffxeqon

# Payment Configuration
RAZORPAY_KEY_ID=your_key_id_here
RAZORPAY_KEY_SECRET=your_key_secret_here

# CORS Origin - Update this with your frontend URL when deployed
CORS_ORIGIN=https://your-frontend-app.onrender.com

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# Console Logging
ENABLE_SQL_LOGGING=false
```

## Frontend Environment Variables (for Render.com Static Site)

```
REACT_APP_API_URL=https://travel-rogue.onrender.com/api
REACT_APP_GOOGLE_MAPS_API_KEY=AIzaSyAONqru6YbrCzb6ZlSROmvBGeyD-6TvXPo
REACT_APP_GEMINI_API_KEY=AIzaSyCHW5d3sySGyimvWKjuqllqiQ2vUz6UYa4
REACT_APP_OPENWEATHER_API_KEY=a5f2bbf9e0cd0082dc1dd6c267ee1b5b
```

## Important Notes:

1. **Backend CORS Update**: After you deploy the frontend, update the `CORS_ORIGIN` in your backend environment variables on Render to match your frontend URL.

2. **Security**: These are your actual API keys. In production, you should:
   - Use different API keys for production vs development
   - Ensure proper API key restrictions (domain restrictions for Google APIs)
   - Keep these environment variables secure

3. **Testing**: After updating, test that:
   - Frontend can connect to backend
   - API calls work correctly
   - CORS is properly configured

## Deployment Steps:

1. **Update Backend CORS** (if frontend is deployed):
   ```
   CORS_ORIGIN=https://your-frontend-app.onrender.com
   ```

2. **Deploy Frontend** with the updated environment variables

3. **Test the connection** between frontend and backend

4. **Update any remaining localhost references** if found
