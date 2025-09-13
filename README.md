# 😊 ChatCode - Real-Time Chat Application

A modern, responsive real-time chat application built with Next.js 14 and TypeScript. Create private chat rooms, share room codes, and communicate instantly with friends and colleagues.

![ChatCode Preview](https://via.placeholder.com/800x400/6366f1/ffffff?text=ChatCode+Real-Time+Chat)

## ✨ Features

- **🏠 Room-Based Chat**: Create and join private chat rooms with unique 6-character codes
- **⚡ Real-Time Messaging**: Instant message delivery using optimized HTTP polling
- **👥 User Management**: Live online user tracking with automatic cleanup
- **📱 Responsive Design**: Seamless experience on desktop, tablet, and mobile
- **🎨 Modern UI**: Beautiful purple/blue gradient design inspired by Discord
- **📋 Easy Sharing**: One-click room code copying to clipboard
- **💬 Message History**: Maintains chat history during active sessions
- **🔄 Auto-Scroll**: Automatically scrolls to new messages
- **🎯 User Avatars**: Colorful avatar system with user initials
- **⏰ Timestamps**: Message timestamps for better conversation tracking

## 🛠️ Technology Stack

### Frontend
- **Next.js 14** - React framework with App Router
- **React 19** - Latest React with concurrent features
- **TypeScript** - Type-safe development
- **Tailwind CSS v4** - Modern utility-first styling
- **shadcn/ui** - High-quality component library
- **Lucide React** - Beautiful icon library

### Backend
- **Next.js API Routes** - Serverless API endpoints
- **Node.js** - JavaScript runtime
- **In-Memory Storage** - Fast real-time data management
- **RESTful API** - Clean HTTP-based communication

### Deployment
- **Vercel** - Optimized serverless deployment
- **Docker** - Containerized deployment option
- **GitHub Actions** - Automated CI/CD pipeline

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- npm, yarn, or pnpm

### Installation

1. **Clone the repository**
   \`\`\`bash
   git clone https://github.com/yourusername/chatcode-app.git
   cd chatcode-app
   \`\`\`

2. **Install dependencies**
   \`\`\`bash
   npm install
   # or
   pnpm install
   # or
   yarn install
   \`\`\`

3. **Run the development server**
   \`\`\`bash
   npm run dev
   # or
   pnpm dev
   # or
   yarn dev
   \`\`\`

4. **Open your browser**
   Navigate to `http://localhost:3000`

## 📖 How to Use

1. **Enter Your Username**: Choose a unique username (up to 20 characters)
2. **Create or Join Room**: 
   - Create a new room to get a 6-character room code
   - Join an existing room using a shared room code
3. **Share Room Code**: Click the copy button to share the room code with others
4. **Start Chatting**: Send messages and see real-time updates from other users
5. **Leave Room**: Click "Leave Room" when you're done chatting

## 🏗️ Project Structure

\`\`\`
├── app/
│   ├── api/chat/route.ts    # Chat API endpoints (GET/POST)
│   ├── globals.css          # Global Tailwind styles
│   ├── layout.tsx           # Root layout with fonts
│   └── page.tsx             # Main chat interface
├── components/ui/           # Reusable UI components
├── lib/utils.ts            # Utility functions
├── public/                 # Static assets
├── .github/workflows/      # GitHub Actions
├── Dockerfile              # Docker configuration
├── docker-compose.yml      # Docker Compose setup
└── vercel.json            # Vercel deployment config
\`\`\`

## 🔧 API Endpoints

### GET `/api/chat?room={roomCode}`
Retrieve messages and users for a specific room.

**Response:**
\`\`\`json
{
  "messages": [
    {
      "id": "1234567890",
      "text": "Hello everyone!",
      "username": "john_doe",
      "timestamp": "2024-01-15T10:30:00Z",
      "color": "bg-blue-500"
    }
  ],
  "users": [
    {
      "username": "john_doe",
      "color": "bg-blue-500"
    }
  ]
}
\`\`\`

### POST `/api/chat`
Handle user actions (join, message, leave, heartbeat).

**Request Body:**
\`\`\`json
{
  "type": "message",
  "data": {
    "text": "Hello everyone!",
    "username": "john_doe",
    "color": "bg-blue-500",
    "roomCode": "ABC123"
  }
}
\`\`\`

## 🚀 Deployment Options

### Vercel (Recommended)
1. **Push to GitHub**: Commit your code to a GitHub repository
2. **Connect to Vercel**: Import your repository on [vercel.com](https://vercel.com)
3. **Deploy**: Vercel automatically builds and deploys your app

### Docker
\`\`\`bash
# Build the image
docker build -t chatcode .

# Run the container
docker run -p 3000:3000 chatcode
\`\`\`

### Docker Compose
\`\`\`bash
docker-compose up -d
\`\`\`

## ⚙️ Configuration

### Environment Variables
No environment variables are required for basic functionality. The app uses in-memory storage for simplicity.

### Customization
- **Colors**: Modify the color palette in `generateUserColor()` function
- **Polling Interval**: Adjust the polling frequency in the `useEffect` hook
- **Message Limits**: Change message history limits in the API route
- **Room Code Length**: Modify the `generateRoomCode()` function

## 🔒 Security Features

- **Input Validation**: All user inputs are validated and sanitized
- **Rate Limiting**: Built-in protection against spam and abuse
- **XSS Protection**: React's built-in XSS protection
- **CSRF Protection**: Next.js built-in CSRF protection
- **Memory Management**: Automatic cleanup of inactive users and old messages

## 🎯 Performance Optimizations

- **Optimized Polling**: Smart polling frequency to balance real-time updates and server load
- **Memory Cleanup**: Automatic removal of inactive users and message history limits
- **Race Condition Prevention**: Mutex-like mechanisms for concurrent user operations
- **Efficient Re-renders**: Optimized React state management
- **Image Optimization**: Next.js automatic image optimization

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Built with [v0.dev](https://v0.dev)** - AI-powered development platform
- **UI Components**: [shadcn/ui](https://ui.shadcn.com)
- **Icons**: [Lucide](https://lucide.dev)
- **Styling**: [Tailwind CSS](https://tailwindcss.com)
- **Framework**: [Next.js](https://nextjs.org)

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/yourusername/chatcode-app/issues) page
2. Create a new issue with detailed information
3. Contact: your.email@example.com

## 🔮 Roadmap

- [ ] WebSocket support for even faster real-time updates
- [ ] User authentication and persistent accounts
- [ ] File sharing and image uploads
- [ ] Message reactions and emojis
- [ ] Private direct messaging
- [ ] Room moderation features
- [ ] Mobile app (React Native)
- [ ] Voice and video chat integration

---

**Made with ❤️ using v0.dev**
