# 🎯 Resumind - AI Resume Analyzer

**Smart feedback for your dream job!**

Resumind is an intelligent resume analysis platform that provides AI-powered feedback to help you optimize your resume for specific job applications. Upload your resume, provide job details, and get comprehensive ATS scores and improvement suggestions.

![React Router](https://img.shields.io/badge/React_Router-7.7.1-CA4245?style=flat&logo=react-router&logoColor=white)
![React](https://img.shields.io/badge/React-19.1.0-61DAFB?style=flat&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-3178C6?style=flat&logo=typescript&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1.4-06B6D4?style=flat&logo=tailwindcss&logoColor=white)

## ✨ Features

- 🤖 **AI-Powered Analysis** - Leverages Claude Sonnet 4 for intelligent resume evaluation
- 📊 **ATS Score** - Get your Applicant Tracking System compatibility score
- 💡 **Detailed Feedback** - Receive actionable tips on:
  - Content quality and relevance
  - Tone and style
  - Structure and formatting
  - Skills presentation
- 📁 **Resume Management** - Track multiple resume submissions and their feedback
- 🔐 **Secure Authentication** - Built-in user authentication via Puter.js
- 📱 **Responsive Design** - Beautiful UI that works on all devices
- 🎨 **Modern UI/UX** - Clean, intuitive interface with smooth animations

## 🚀 Getting Started

### Prerequisites

- Node.js (v20 or higher recommended)
- npm or pnpm

### Installation

1. Clone the repository:
```bash
git clone https://github.com/zekedavidson/ai-resume-analyzer.git
cd ai-resume-analyzer
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

Your application will be available at `http://localhost:5173`

## 📖 How to Use

1. **Sign In** - Authenticate using Puter.js authentication
2. **Upload Resume** - Navigate to the upload page
3. **Provide Job Details** - Enter:
   - Company name
   - Job title
   - Job description
4. **Upload PDF** - Drag and drop or select your resume PDF
5. **Get Feedback** - AI analyzes your resume and provides:
   - Overall score
   - ATS compatibility score
   - Detailed feedback on multiple aspects
   - Specific improvement suggestions
6. **Review & Improve** - View your resume alongside AI feedback
7. **Track Progress** - Access all your analyzed resumes from the homepage

## 🛠️ Tech Stack

### Frontend
- **React 19.1.0** - UI library
- **React Router 7.7.1** - Routing and SSR
- **TypeScript** - Type safety
- **TailwindCSS 4.1.4** - Styling
- **Zustand** - State management

### Backend & Services
- **Puter.js** - Authentication, file storage, and AI services
- **Claude Sonnet 4** - AI model for resume analysis
- **PDF.js** - PDF processing and image conversion

### Key Libraries
- `react-dropzone` - File upload interface
- `pdfjs-dist` - PDF to image conversion
- `clsx` & `tailwind-merge` - Utility class management

## 📁 Project Structure

```
ai-resume-analyzer/
├── app/
│   ├── components/       # React components
│   │   ├── Navbar.tsx
│   │   ├── FileUploader.tsx
│   │   ├── ResumeCard.tsx
│   │   ├── Summary.tsx
│   │   ├── ATS.tsx
│   │   └── Details.tsx
│   ├── lib/             # Utility functions
│   │   ├── puter.ts     # Puter.js integration
│   │   ├── pdf2img.ts   # PDF conversion
│   │   └── utils.ts
│   ├── routes/          # Application routes
│   │   ├── home.tsx     # Dashboard
│   │   ├── upload.tsx   # Upload page
│   │   ├── resume.tsx   # Resume review page
│   │   └── auth.tsx     # Authentication
│   └── app.css          # Global styles
├── constants/
│   └── index.ts         # AI prompts and configurations
├── public/
│   ├── images/          # Static images
│   └── icons/           # Icon assets
└── types/               # TypeScript type definitions
```

## 🔧 Available Scripts

- `npm run dev` - Start development server with HMR
- `npm run build` - Create production build
- `npm run start` - Start production server
- `npm run typecheck` - Run TypeScript type checking

## 🚀 Deployment

### Render.com (Recommended)

#### Option 1: Static Site Deployment (Easiest)

This app is configured as an SPA (`ssr: false`), making it perfect for static hosting:

1. **Create a Static Site** on Render.com
2. **Configure:**
   ```
   Build Command: npm install && npm run build
   Publish Directory: build/client
   ```
3. **Add Rewrite Rule** (Critical for routing):
   - Source: `/*`
   - Destination: `/index.html`
   - Action: `Rewrite`

4. **Deploy!** Your app will be live at `https://your-app.onrender.com`

#### Option 2: Web Service with SSR

For server-side rendering (better SEO):

1. **Update `react-router.config.ts`:**
   ```typescript
   export default {
     ssr: true,  // Change from false
   } satisfies Config;
   ```

2. **Create a Web Service** on Render.com:
   ```
   Build Command: npm install && npm run build
   Start Command: npm run start
   ```

> 📖 **Detailed deployment guide:** See [RENDER_FIX.md](./RENDER_FIX.md) for troubleshooting

### Docker Deployment

Build and run using Docker:

```bash
# Build the image
docker build -t resumind .

# Run the container
docker run -p 3000:3000 resumind
```

**Note:** Enable SSR mode (`ssr: true`) before using Docker deployment.

The containerized application can be deployed to:
- AWS ECS
- Google Cloud Run
- Azure Container Apps
- Digital Ocean App Platform
- Fly.io
- Railway

## 🎨 Features in Detail

### AI Analysis Categories

1. **ATS Compatibility**
   - Keyword optimization
   - Format compatibility
   - Parsing friendliness

2. **Content Quality**
   - Relevance to job description
   - Achievement quantification
   - Impact demonstration

3. **Tone & Style**
   - Professional language
   - Active voice usage
   - Clarity and conciseness

4. **Structure**
   - Section organization
   - Visual hierarchy
   - Readability

5. **Skills Presentation**
   - Relevant skills highlighting
   - Technical proficiency demonstration
   - Skill-job alignment

## 🔐 Authentication & Storage

This application uses **Puter.js** for:
- User authentication
- File storage (resume PDFs and images)
- Key-value storage for resume metadata
- AI chat services

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Built with [React Router](https://reactrouter.com/)
- Powered by [Puter.js](https://puter.com/)
- AI analysis by Claude Sonnet 4
- UI components styled with [TailwindCSS](https://tailwindcss.com/)

## 📧 Contact

For questions or feedback, please open an issue on GitHub.

---

Built with ❤️ to help job seekers land their dream jobs.
