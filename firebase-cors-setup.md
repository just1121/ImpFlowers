# Firebase Storage CORS Configuration

## The Problem
Firebase Storage is blocking uploads from your Render.com domain due to CORS policy.

## Solution: Configure Firebase Storage CORS Rules

### Step 1: Install Firebase CLI (if not already installed)
```bash
npm install -g firebase-tools
```

### Step 2: Login to Firebase
```bash
firebase login
```

### Step 3: Create a CORS configuration file
Create a file called `cors.json` with this content:
```json
[
  {
    "origin": ["https://importantflowers.onrender.com", "http://localhost:8001", "http://localhost:8000"],
    "method": ["GET", "POST", "PUT", "DELETE", "HEAD", "OPTIONS"],
    "maxAgeSeconds": 3600,
    "responseHeader": ["Content-Type", "Authorization", "Content-Length", "User-Agent", "x-goog-resumable"]
  }
]
```

### Step 4: Apply CORS configuration
```bash
gsutil cors set cors.json gs://importantflowers-61b97.appspot.com
```

### Step 5: Verify the configuration
```bash
gsutil cors get gs://importantflowers-61b97.appspot.com
```

## Alternative: Use Firebase Console

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Select your project: `importantflowers-61b97`
3. Go to Storage → Rules
4. Update the rules to allow your domain

## Quick Fix: Temporary Workaround

If you can't configure CORS immediately, the app will fall back to text covers, which still work perfectly for your publication schedule. 