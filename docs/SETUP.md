# Setup Instructions

## Prerequisites

- Node.js v16 or higher
- npm or yarn
- MongoDB (local or cloud instance)
- React Native CLI
- Android Studio (for Android development)
- Xcode (for iOS development)

## Backend Setup

### 1. Install Dependencies

```bash
cd backend
npm install
```

### 2. Configure Environment Variables

Create a `.env` file in the backend directory:

```bash
cp .env.example .env
```

Edit `.env` and add your configuration:

```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/dubai-price-comparison
JWT_SECRET=your_secret_key_here
JWT_EXPIRE=7d
```

### 3. Start MongoDB

If using MongoDB locally:

```bash
mongod
```

Or use MongoDB Atlas (cloud):
- Go to https://www.mongodb.com/cloud/atlas
- Create a cluster and get your connection string
- Add it to `.env` as MONGODB_URI

### 4. Start Backend Server

```bash
npm run dev
```

Server will run on `http://localhost:5000`

## Frontend Setup

### 1. Install Dependencies

```bash
cd frontend
npm install
```

### 2. Install pods (iOS only)

```bash
cd ios
pod install
cd ..
```

### 3. Update API URL

Edit `frontend/src/services/api.js` and update the API_BASE_URL:

```javascript
const API_BASE_URL = 'http://your-backend-url/api';
```

For local development on Android emulator:
```javascript
const API_BASE_URL = 'http://10.0.2.2:5000/api';
```

### 4. Run on Android

```bash
npm run android
```

### 5. Run on iOS

```bash
npm run ios
```

## Next Steps

1. ✅ Backend is running on port 5000
2. ✅ Frontend is connected to backend
3. 🔄 Start building features incrementally

For more details, see API.md and ARCHITECTURE.md
