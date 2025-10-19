# ReachInbox Onebox - Email Aggregator

A modern email aggregator web application with AI-powered categorization, smart filtering, and unified inbox management across multiple accounts.

## 🚀 Features

### Core Functionality
- **Unified Inbox**: Aggregate emails from multiple accounts in one clean interface
- **AI Categorization**: Automatically categorize emails into:
  - 🟢 **Interested** - High-value opportunities and important communications
  - 🟡 **Follow-up** - Messages requiring action or response
  - ⚪ **Not Interested** - Low-priority or promotional content
- **Smart Search**: Search emails by subject, sender, or content (simulating Elasticsearch)
- **Advanced Filters**: Filter by account and folder (Inbox, Sent, Drafts)
- **Slack Notifications**: Mock notification system logs categorization actions

### User Experience
- **Beautiful UI**: Modern, clean interface inspired by Linear and Superhuman
- **Dark Mode**: Toggle between light and dark themes
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Real-time Updates**: Instant UI updates when categorizing emails
- **Empty States**: Thoughtful empty and loading states for better UX

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Shadcn UI** - Component library
- **TanStack Query** - Data fetching and caching
- **Wouter** - Lightweight routing
- **date-fns** - Date formatting

### Backend
- **Node.js** - Runtime
- **Express** - Web framework
- **TypeScript** - Type safety
- **Zod** - Schema validation
- **In-Memory Storage** - Fast mock data storage

## 📁 Project Structure

```
/
├── client/                 # Frontend application
│   ├── src/
│   │   ├── components/    # React components
│   │   │   ├── ui/       # Shadcn UI components
│   │   │   ├── CategoryBadge.tsx
│   │   │   ├── EmailList.tsx
│   │   │   ├── EmailListItem.tsx
│   │   │   ├── EmailDetail.tsx
│   │   │   ├── app-sidebar.tsx
│   │   │   └── ThemeToggle.tsx
│   │   ├── pages/        # Page components
│   │   │   └── Dashboard.tsx
│   │   ├── lib/          # Utilities
│   │   ├── App.tsx       # Main app component
│   │   └── index.css     # Global styles
│   └── index.html
├── server/                # Backend application
│   ├── routes.ts         # API endpoints
│   ├── storage.ts        # In-memory data storage
│   └── index.ts          # Server entry point
├── shared/               # Shared types and schemas
│   └── schema.ts         # Data models and validation
└── README.md
```

## 🚦 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn

### Installation & Running

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the application:**
   ```bash
   npm run dev
   ```

3. **Open your browser:**
   Navigate to `http://localhost:5000`

The application runs both frontend and backend on a single port (5000) using Vite's development server.

## 🎯 API Endpoints

### Get All Emails
```
GET /api/emails
Query params:
  - account (optional): Filter by email account
  - folder (optional): Filter by folder (inbox, sent, drafts)
  - search (optional): Search by subject, sender, or content
```

### Get Email by ID
```
GET /api/emails/:id
```

### Update Email Category
```
PATCH /api/emails/:id/category
Body: { category: "Interested" | "Follow-up" | "Not Interested" }
```

## 📊 AI Categorization Logic

The application uses rule-based categorization to simulate AI:

- **Interested**: Emails containing keywords like "partnership", "opportunity", "proposal", "interested"
- **Follow-up**: Emails containing "meeting", "follow-up", "re:", "confirm", "schedule"
- **Not Interested**: Promotional emails, newsletters, automated notifications

Users can manually override categories by clicking the category buttons in the email detail view.

## 🔔 Slack Notification System

When an email is categorized, the system logs a formatted notification to the console:

```
🔔 [Slack Notification Mock]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📧 Email Categorized
From: Sarah Johnson
Subject: Q4 Partnership Proposal
Category: Interested
Timestamp: 2025-10-19T10:30:00.000Z
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 🎨 Design System

The application follows a carefully crafted design system:

- **Colors**: Professional blue accent with category-specific colors
- **Typography**: Inter font family for clean, modern look
- **Spacing**: Consistent 8px grid system
- **Components**: Reusable shadcn components with custom styling
- **Interactions**: Subtle hover states and smooth transitions

## 🧪 Testing

The application includes comprehensive data-testid attributes for end-to-end testing:

- All interactive elements (buttons, inputs, selects)
- Email list items and details
- Navigation elements
- Dynamic content

## 📝 Future Enhancements

- Real AI integration using OpenAI or similar services
- Actual Slack webhook integration
- Email compose and reply functionality
- Persistent database storage
- Email threading and conversation view
- Attachment support
- Multiple email account OAuth integration
- Email sync with real providers (Gmail, Outlook, etc.)

## 👨‍💻 Development

### Key Technologies
- **Vite**: Fast development and build tool
- **TypeScript**: Full type safety across frontend and backend
- **Zod**: Runtime type validation
- **TanStack Query**: Efficient data fetching with caching

### Development Commands
```bash
npm run dev      # Start development server
npm run build    # Build for production
```

## 📄 License

This project is created as a demonstration/assignment project for ReachInbox.

## 🙏 Acknowledgments

- Design inspired by Linear and Superhuman
- UI components from Shadcn UI
- Icons from Lucide React

---

**Built with ❤️ for ReachInbox**
