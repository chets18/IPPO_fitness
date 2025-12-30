# 🏋️ IPPO Fitness - AI-Powered Workout Tracker

> **A fun project that started as a personal challenge to build something cool with AI and fitness tracking!**

IPPO Fitness is a modern, AI-powered fitness web application that uses computer vision to track your workouts in real-time. Built with React, TypeScript, and MediaPipe Pose Detection, it automatically counts your pushups and squats using just your webcam - no wearables needed!

## 🎯 Why I Built This

This project started as a fun experiment to combine my interest in AI/ML with fitness tracking. I wanted to create something that:

- **Makes fitness tracking accessible** - No need for expensive fitness trackers or gym equipment
- **Uses cutting-edge AI** - Leverages MediaPipe's pose detection for accurate movement tracking
- **Feels like a game** - Gamified experience with scores, streaks, and achievements
- **Works anywhere** - Just need a webcam and a browser

What began as a weekend project quickly evolved into a full-featured fitness app with real-time tracking, progress analytics, and a sleek modern UI!

## ✨ Features

### 🤖 AI-Powered Workout Tracking
- **Real-time Pose Detection**: Uses MediaPipe to track your body movements through your webcam
- **Automatic Rep Counting**: Accurately counts pushups and squats without manual input
- **Visual Feedback**: See your pose landmarks overlaid on the video feed
- **Form Analysis**: Tracks workout stages (up/down positions) for proper form

### 📊 Comprehensive Dashboard
- **Elite Stats View**: Track your total power index, streaks, and workout history
- **Performance Charts**: Visualize your progress over the last 7 days with interactive charts
- **Ranking System**: Progress through ranks (IPPO, etc.) based on your performance
- **Session Logs**: Detailed history of all your workout sessions

### 🎵 Enhanced Training Experience
- **Music Player**: Built-in music player with different vibe modes (Calm, Intense, Beast Mode)
- **Custom Playlists**: Import and play your own workout music
- **Real-time Stats**: See your rep count, score, and time remaining during workouts

### ⏰ Smart Reminders
- **Training Alarms**: Set recurring reminders for your workout sessions
- **Interval Timer**: Customizable countdown timer with custom alarm sounds
- **Day Selection**: Choose which days of the week to receive reminders

### 🎨 Modern UI/UX
- **Beautiful Design**: Sleek, modern interface with smooth animations
- **Dark Mode Support**: Eye-friendly dark theme for focused workouts
- **Responsive Layout**: Works seamlessly on desktop and mobile devices
- **Smooth Animations**: Powered by Framer Motion for fluid interactions

## 🛠️ Tech Stack

### Frontend
- **React 18** - Modern UI library
- **TypeScript** - Type-safe development
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **Framer Motion** - Smooth animations
- **Radix UI** - Accessible component primitives
- **Recharts** - Beautiful data visualizations
- **Wouter** - Lightweight routing

### AI/ML
- **MediaPipe Pose** - Real-time pose detection
- **React Webcam** - Webcam integration
- **Custom Workout Logic** - Pushup and squat detection algorithms

### Backend
- **Express.js** - RESTful API server
- **Drizzle ORM** - Type-safe database queries
- **WebSockets** - Real-time communication (via ws)

### Database
- **SQLite** (or your preferred database via Drizzle)

## 📁 Project Structure

```
IPPOfitness/
├── pushups/
│   ├── client/              # React frontend application
│   │   ├── src/
│   │   │   ├── components/  # Reusable UI components
│   │   │   ├── hooks/       # Custom React hooks
│   │   │   ├── lib/         # Utility functions
│   │   │   └── pages/       # Page components
│   │   └── public/          # Static assets
│   ├── server/              # Express backend
│   │   ├── index.ts         # Server entry point
│   │   ├── routes.ts        # API routes
│   │   └── db.ts            # Database setup
│   ├── shared/              # Shared types and schemas
│   └── package.json         # Dependencies
└── zpython/                 # Python utilities (if any)
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ and npm
- A webcam for workout tracking
- Modern browser with WebRTC support

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd IPPOfitness
   ```

2. **Install dependencies**
   ```bash
   cd pushups
   npm install
   ```

3. **Set up the database**
   ```bash
   npm run db:push
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:5173` (or the port shown in your terminal)

### Building for Production

```bash
npm run build
npm start
```

## 🎮 How to Use

1. **Start a Workout**
   - Navigate to the Home page
   - Select a workout (Pushups, Squats, etc.)
   - Allow camera permissions when prompted
   - Position yourself so your full body is visible
   - Click "START" and begin your workout!

2. **Track Your Progress**
   - View your stats on the Dashboard
   - Check your workout history
   - Monitor your streaks and achievements

3. **Set Reminders**
   - Go to the Alarm page
   - Create training alarms for consistent workouts
   - Use the interval timer for timed sessions

## 🚀 Deployment

Ready to share your fitness app with the world? Check out the comprehensive [**Deployment Guide**](./DEPLOYMENT_GUIDE.md) for step-by-step instructions on:

- 📤 Pushing your project to GitHub
- ☁️ Deploying to Vercel (recommended for React apps)
- 🌐 Deploying to Netlify (great for static sites)
- 🔧 Troubleshooting common deployment issues

**Quick Deploy to Vercel:**
1. Push your code to GitHub
2. Import your repository in [Vercel](https://vercel.com)
3. Set build directory to `pushups` and output to `dist/public`
4. Deploy! 🎉

**Quick Deploy to Netlify:**
1. Push your code to GitHub
2. Import your repository in [Netlify](https://netlify.com)
3. Set base directory to `pushups`, build command to `npm run build`, and publish directory to `dist/public`
4. Deploy! 🎉

## 🔒 Privacy & Security

- **All processing is local**: Pose detection runs entirely in your browser
- **No video storage**: Your webcam feed is never recorded or stored
- **Local-first**: Your workout data is stored locally (or on your own server)

## 🤝 Contributing

This started as a personal project, but contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Share your workout achievements!

## 📝 License

MIT License - Feel free to use this project for learning or building your own fitness apps!

## 🙏 Acknowledgments

- **MediaPipe** - For the amazing pose detection technology
- **Radix UI** - For accessible component primitives
- **The open-source community** - For all the amazing tools that made this possible

---

**Built with ❤️ as a fun project to explore AI and fitness tracking**

*Remember: Consistency beats intensity. Keep pushing! 💪*

