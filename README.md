# UrbanStyle Feedback Management System

A comprehensive feedback management portal for UrbanStyle Retail that aggregates customer feedback from multiple sources, analyzes sentiment and themes using AI, and provides actionable insights through interactive dashboards.

## 🎯 Features

- **🤖 AI-Powered Chatbot**: Interactive AI assistant for Q&A, issue resolution, and insights
- **🧠 Advanced AI Analysis**: OpenAI-powered sentiment analysis, theme extraction, and summarization
- **💡 AI Resolution Suggestions**: Step-by-step AI-generated solutions for customer issues
- **📊 Auto-Categorization**: AI automatically categorizes feedback into themes
- **Centralized Feedback Portal**: Aggregate feedback from Microsoft Forms, emails, QR codes, and other sources
- **Role-Based Access Control**: Different views for Admin, CX Lead, and Store Managers
- **Interactive Dashboards**: Visual analytics with charts and graphs
- **File Upload Support**: Upload CSV or JSON files exported from Microsoft Forms
- **Store & Product Analysis**: Detailed breakdowns by store and product category
- **AI-Generated Responses**: Context-aware customer service response suggestions

## 🏗️ Architecture

### Backend (Node.js/Express)
- RESTful API with Express.js
- File-based storage (JSON) - simulates database
- CSV/JSON file parsing for data import
- **OpenAI Integration** for advanced AI capabilities
- AI service with fallback for sentiment analysis and theme extraction
- AI chatbot endpoint for Q&A
- AI-powered resolution suggestions
- Role-based middleware for access control

### Frontend (React)
- Modern React with Hooks
- React Router for navigation
- Chart.js for data visualization
- Responsive design with modern UI
- Context API for state management

## 📁 Project Structure

```
urbanStyle/
├── backend/
│   ├── data/
│   │   ├── feedback.json          # Feedback data storage
│   │   ├── users.json             # User credentials
│   │   └── sample-feedback.csv    # Sample CSV file
│   ├── middleware/
│   │   └── roleMiddleware.js      # Role-based access control
│   ├── routes/
│   │   ├── authRoutes.js          # Authentication endpoints
│   │   ├── feedbackRoutes.js      # Feedback CRUD operations
│   │   ├── analyticsRoutes.js     # Analytics endpoints
│   │   └── aiRoutes.js             # AI chatbot and AI features
│   ├── services/
│   │   ├── aiService.js           # AI analysis logic
│   │   ├── csvService.js          # CSV parsing
│   │   └── feedbackService.js     # Feedback data operations
│   ├── uploads/                   # Temporary file uploads
│   ├── package.json
│   └── server.js                  # Express server
│
├── frontend/
│   ├── src/
│   │   ├── api/
│   │   │   └── api.js             # Axios configuration
│   │   ├── components/
│   │   │   ├── Charts.jsx         # Chart components
│   │   │   ├── FeedbackTable.jsx  # Feedback table
│   │   │   └── Navbar.jsx         # Navigation bar
│   │   ├── context/
│   │   │   └── AuthContext.jsx     # Authentication context
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx      # Main dashboard
│   │   │   ├── Login.jsx          # Login page
│   │   │   ├── Upload.jsx         # File upload page
│   │   │   ├── FeedbackList.jsx   # Feedback listing
│   │   │   └── Reports.jsx        # Analytics reports
│   │   ├── App.jsx                # Main app component
│   │   ├── App.css                # Global styles
│   │   ├── index.css
│   │   └── main.jsx               # Entry point
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- (Optional) OpenAI API key for enhanced AI features - Get from https://platform.openai.com/api-keys

### Installation Steps

#### 1. Install Backend Dependencies

```bash
cd backend
npm install
```

#### 2. Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

#### 3. Start the Backend Server

```bash
cd backend
npm start
```

The backend will run on `http://localhost:5000`

#### 4. Start the Frontend Development Server

In a new terminal:

```bash
cd frontend
npm run dev
```

The frontend will run on `http://localhost:5173` (or another port if 5173 is busy)

### 5. (Optional) Configure OpenAI API for Enhanced AI

For full AI capabilities, set up OpenAI API:

```bash
cd backend
# Create .env file
echo "OPENAI_API_KEY=your_openai_api_key_here" > .env
```

**Note**: The system works without an API key using intelligent fallbacks. See [AI_FEATURES.md](./AI_FEATURES.md) for details.

## 🔐 Default Login Credentials

| Role | Username | Password | Access Level |
|------|----------|----------|--------------|
| Admin | `admin` | `admin123` | Full access - can upload, view all feedback, all analytics |
| CX Lead | `cxlead` | `cx123` | View all feedback and analytics, cannot upload |
| Manager | `manager1` | `manager123` | View only Mumbai store feedback and analytics |

## 📊 Features by Role

### Admin
- Upload CSV/JSON feedback files
- View all feedback from all stores
- Access complete analytics and reports
- View store-wise and product-wise breakdowns

### CX Lead
- View all feedback from all stores
- Access complete analytics and reports
- View store-wise and product-wise breakdowns
- Cannot upload files

### Store Manager
- View feedback only from their assigned store
- View analytics filtered to their store
- Cannot upload files or view other stores' data

## 📤 Uploading Feedback Data

### CSV Format

```csv
store,channel,product,rating,comment,createdAt
Mumbai,Microsoft Form,T-Shirt,2,"delivery was late",2025-01-15
Delhi,QR Code,Jeans,4,"good quality product",2025-01-16
```

### JSON Format

```json
[
  {
    "store": "Mumbai",
    "channel": "Microsoft Form",
    "product": "T-Shirt",
    "rating": 2,
    "comment": "delivery was late",
    "createdAt": "2025-01-15"
  }
]
```

**Required Fields:**
- `store`: Store name
- `rating`: Rating (1-5)
- `comment`: Feedback comment

**Optional Fields:**
- `channel`: Source channel (defaults to "Microsoft Form")
- `product`: Product category (defaults to "General")
- `createdAt`: Date in YYYY-MM-DD format (defaults to current date)

## 🤖 AI-Powered Features

### AI Chatbot Assistant
- **Access**: Click "🤖 AI Assistant" in navbar or floating button
- **Capabilities**:
  - Answer questions about customer feedback
  - Identify main issues and suggest resolutions
  - Provide sentiment analysis insights
  - Analyze store performance
  - Answer questions about trends

### Advanced AI Analysis
1. **Sentiment Analysis**: OpenAI-powered classification (positive/negative/neutral)
2. **Theme Extraction**: AI understands context, not just keywords
3. **Summary Generation**: GPT-generated executive summaries
4. **Response Suggestions**: Context-aware customer service responses
5. **Resolution Steps**: Step-by-step AI-generated solutions
6. **Auto-Categorization**: Automatic feedback categorization

**See [AI_FEATURES.md](./AI_FEATURES.md) for complete AI documentation.**

## 📈 Analytics & Reports

### Dashboard
- Overview statistics (total, positive, negative feedback)
- Satisfaction rate
- AI-generated summary
- Key themes visualization
- Rating distribution

### Reports Page
- Detailed theme analysis
- Store performance comparison
- Product performance metrics
- Rating distribution charts
- Store-wise breakdown tables

## 🔧 API Endpoints

### Authentication
- `POST /auth/login` - User login
- `GET /auth/me` - Get current user

### Feedback
- `GET /feedback` - Get all feedback (filtered by role)
- `GET /feedback/:id` - Get single feedback with AI response and category
- `POST /feedback` - Add new feedback (Admin/CX only)
- `POST /feedback/upload` - Upload CSV/JSON file (Admin only)

### Analytics
- `GET /analytics/summary` - Get overall analytics summary (AI-powered)
- `GET /analytics/stores` - Get store-wise breakdown (Admin/CX only)
- `GET /analytics/products` - Get product-wise breakdown (Admin/CX only)
- `GET /analytics/ratings` - Get rating distribution

### AI Features
- `POST /ai/chat` - Chat with AI assistant
- `GET /ai/resolutions/:feedbackId` - Get AI-powered resolution suggestions
- `POST /ai/categorize` - Auto-categorize feedback
- `POST /ai/batch-analyze` - Batch analyze feedback with AI

## 🛠️ Technology Stack

### Backend
- **Express.js** - Web framework
- **Multer** - File upload handling
- **csv-parser** - CSV file parsing
- **CORS** - Cross-origin resource sharing

### Frontend
- **React 19** - UI library
- **React Router** - Routing
- **Axios** - HTTP client
- **Chart.js** - Data visualization
- **Vite** - Build tool

## 📝 Notes

- This is a prototype application. Passwords are stored in plain text (not encrypted) for demonstration purposes.
- Data is stored in JSON files (file-based storage) instead of a database for simplicity.
- The AI analysis uses rule-based logic to simulate AI functionality. In production, you would integrate with OpenAI API or similar services.
- The `uploads/` directory is used for temporary file storage during uploads.

## 🎨 UI Features

- Modern, responsive design
- Gradient color scheme
- Interactive charts and graphs
- Filterable feedback tables
- Role-based navigation
- Loading states and error handling
- Clean, professional interface

## 🔄 Data Flow

1. **Data Import**: Admin uploads CSV/JSON file from Microsoft Forms
2. **Storage**: Data is parsed and stored in `feedback.json`
3. **Analysis**: AI service analyzes sentiment and extracts themes
4. **Visualization**: Frontend displays data in charts and tables
5. **Filtering**: Users can filter by store, rating, and search comments
6. **Reports**: Analytics are generated on-demand for stakeholders

## 🚧 Future Enhancements

- Database integration (MongoDB/PostgreSQL)
- Email notifications
- Export reports to PDF
- Advanced filtering and search
- Feedback response tracking
- User management interface
- API authentication with JWT tokens
- AI model fine-tuning for better accuracy
- Multi-language support with AI translation

## 📞 Support

For issues or questions, please refer to the codebase or contact the development team.

---

**Built for UrbanStyle Retail** - Transforming customer feedback into actionable insights.

