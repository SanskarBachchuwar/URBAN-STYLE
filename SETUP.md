# Quick Setup Guide

## Step-by-Step Installation

### 1. Navigate to Project Directory
```bash
cd urbanStyle
```

### 2. Install Backend Dependencies
```bash
cd backend
npm install
```

**Expected output:** Dependencies will be installed including:
- express
- cors
- multer
- csv-parser
- openai

### 3. Install Frontend Dependencies
```bash
cd ../frontend
npm install
```

**Expected output:** Dependencies will be installed including:
- react
- react-dom
- react-router-dom
- axios
- chart.js
- react-chartjs-2

### 4. Start Backend Server

In the `backend` directory:
```bash
npm start
```

**Expected output:**
```
Backend running on http://localhost:5000
```

### 5. Start Frontend Server

Open a **new terminal window** and navigate to `frontend` directory:
```bash
cd frontend
npm run dev
```

**Expected output:**
```
  VITE v7.x.x  ready in xxx ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```

### 6. Access the Application

Open your browser and navigate to:
```
http://localhost:5173
```

## Login Credentials

Use any of these credentials to login:

| Role | Username | Password |
|------|----------|----------|
| Admin | `admin` | `admin123` |
| CX Lead | `cxlead` | `cx123` |
| Manager | `manager1` | `manager123` |

## Testing the Application

### 1. Login
- Go to http://localhost:5173
- Login with admin credentials
- You should see the dashboard

### 2. View Dashboard
- See overview statistics
- View AI-generated summary
- Check charts and visualizations

### 3. Upload Feedback (Admin only)
- Navigate to "Upload" in the navbar
- Upload the sample CSV file from `backend/data/sample-feedback.csv`
- Or create your own CSV/JSON file

### 4. View Feedback
- Click "Feedback" in navbar
- Filter by store, rating, or search comments
- View all feedback entries

### 5. View Reports
- Click "Reports" in navbar
- See detailed analytics
- View store and product breakdowns

## Troubleshooting

### Backend won't start
- Make sure port 5000 is not in use
- Check that all dependencies are installed: `npm install` in backend directory
- Verify Node.js version is 14 or higher: `node --version`

### Frontend won't start
- Make sure port 5173 is not in use (or use the port shown in terminal)
- Check that all dependencies are installed: `npm install` in frontend directory
- Clear node_modules and reinstall if needed

### CORS errors
- Make sure backend is running on port 5000
- Check that frontend API base URL in `frontend/src/api/api.js` is `http://localhost:5000`

### Login not working
- Verify backend is running
- Check browser console for errors
- Ensure user credentials match those in `backend/data/users.json`

### No data showing
- Upload sample data using the Upload page (Admin only)
- Or check that `backend/data/feedback.json` has data
- Refresh the page after uploading

## File Structure Verification

Make sure these directories exist:
```
backend/
  ├── data/
  │   ├── feedback.json
  │   ├── users.json
  │   └── sample-feedback.csv
  ├── uploads/ (created automatically)
  ├── middleware/
  ├── routes/
  ├── services/
  └── server.js

frontend/
  ├── src/
  │   ├── api/
  │   ├── components/
  │   ├── context/
  │   ├── pages/
  │   └── App.jsx
  └── package.json
```

## Next Steps

1. **Test all features** with different user roles
2. **Upload your own data** from Microsoft Forms
3. **Explore analytics** and reports
4. **Customize** the UI or add features as needed

## Development Commands

### Backend
```bash
cd backend
npm start          # Start server
npm run dev        # Start with nodemon (if installed)
```

### Frontend
```bash
cd frontend
npm run dev        # Start development server
npm run build      # Build for production
npm run preview    # Preview production build
```

---

**Happy Coding! 🚀**

