<div align="center">

# 🚀 Tap to Build

### *Build Beautiful Landing Pages in Minutes*

<img src="Frontend/assets/gp.gif" width="700" alt="Tap to Build Demo">

[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)

[Features](#-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Deployment](#-deployment)

---

</div>

## 📖 About

**Tap to Build** is an intuitive, browser-based platform that empowers small businesses to create professional landing pages without any coding knowledge. Through a seamless multi-step workflow, users can design, customize, and deploy their web presence in minutes.

> 🎓 **Graduation Project Note**  
> This web platform is part of our graduation project. The complete project includes:
> - **Tap to Build** (Web Platform) - *Built by me [@Narjes-almasri] & [Friend's Name]*
> - **Refqa** (Mobile App) - *Built by [Colleague 1], [Colleague 2], [Colleague 3]*

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎨 **Intuitive Builder**
- Step-by-step guided workflow
- Real-time preview as you build
- No coding required

### 🔐 **Secure Authentication**
- Bcrypt password hashing
- Session management
- Admin dashboard access

</td>
<td width="50%">

### 🎯 **Complete Customization**
- Color palette selection
- Logo creation & upload
- Content editing tools

### 📊 **Admin Tools**
- Site management dashboard
- Evaluation system
- Analytics overview

</td>
</tr>
</table>

---

## 🎬 See It In Action

<div align="center">
<img src="Frontend/assets/nar.gif" width="700" alt="Final Result Showcase">

*From idea to live website in just a few clicks*

</div>

---

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18 or higher
- **npm** (comes with Node.js)

### Installation
```bash
# Navigate to backend directory
cd Backend

# Install dependencies
npm install

# Start the development server
npm start
```

🎉 **That's it!** Open your browser and visit `http://localhost:3000`

---

## 📂 Project Structure
```
Tap-to-Build/
├── 🎨 Frontend/
│   ├── 📄 User Flow Pages
│   │   ├── sign_up.html          # User registration
│   │   ├── login.html             # Authentication
│   │   ├── profile_setup.html     # Profile creation
│   │   ├── app_setup.html         # App configuration
│   │   ├── color_palette.html     # Brand colors
│   │   ├── generation.html        # Logo creation
│   │   ├── build_preview.html     # Live editor
│   │   └── final_preview.html     # Final review
│   │
│   ├── 👨‍💼 Admin Pages
│   │   ├── admin_login.html       # Admin auth
│   │   ├── admin_dashboard.html   # Control panel
│   │   ├── saved_websites.html    # Site manager
│   │   └── saved_evaluations.html # Reviews
│   │
│   ├── 🛠️ Utilities
│   │   └── data-collector.js      # Session manager
│   │
│   └── 🎨 Assets
│       ├── images/                # Images & icons
│       └── assets/                # GIFs & media
│
└── ⚙️ Backend/
    ├── server.js                  # Express API
    ├── validate-config.js         # Schema validator
    ├── site-config.schema.json    # JSON schema
    ├── site-config.example.json   # Minimal example
    └── full-site-data.example.json # Complete example
```

---

## 🔌 API Reference

### Authentication Endpoints

#### **POST** `/api/signup`
Create a new user account
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

#### **POST** `/api/login`
Authenticate existing user
```json
{
  "email": "john@example.com",
  "password": "securePassword123"
}
```

### Site Configuration

#### **POST** `/api/site-config`
Submit complete site configuration (validated against JSON schema)

---

## 💾 Data Collection System

The builder automatically saves your progress in the browser's session storage. Our data collector seamlessly aggregates everything into a single configuration.

### Usage Example
```javascript
// Collect all session data
const siteData = SiteDataCollector.collectAllData();

// Submit to backend
await SiteDataCollector.sendToBackend('/api/site-config');

// Or download as JSON
SiteDataCollector.downloadAsJSON();
```

### Session Storage Keys

| Key | Description |
|-----|-------------|
| `userProfile` | User profile information |
| `selectedPalette` | Chosen color scheme |
| `generatedLogo` / `uploadedLogo` | Logo data |
| `appName` | Application name |
| `selectedCatalog` | Product catalog |
| `pageContent` | Page content data |
| `pageImages` | Uploaded images |
| `logoSize`, `logoBorderRadius` | Logo styling |
| `logoViewerZoom`, `logoViewerOffset*` | Logo viewer state |

---

## ✅ Validation & Testing

Run schema validation against example configurations:
```bash
cd Backend
npm run validate
```

**Example Files:**
- 📝 **Minimal:** `site-config.example.json`
- 📋 **Complete:** `full-site-data.example.json`

---

## 🌐 Deployment

### Frontend (Static Hosting)

Deploy to any static hosting platform:

<table>
<tr>
<td align="center" width="25%">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="60" />
<br><strong>AWS S3</strong>
</td>
<td align="center" width="25%">
<img src="https://www.vectorlogo.zone/logos/netlify/netlify-icon.svg" width="60" />
<br><strong>Netlify</strong>
</td>
<td align="center" width="25%">
<img src="https://www.vectorlogo.zone/logos/vercel/vercel-icon.svg" width="60" />
<br><strong>Vercel</strong>
</td>
<td align="center" width="25%">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="60" />
<br><strong>GitHub Pages</strong>
</td>
</tr>
</table>

Simply point your hosting service to the `Frontend/` directory.

### Backend (API Server)

**Options:**
1. **Keep Express Server** - Deploy as-is to any Node.js hosting
2. **Go Serverless** - Migrate to AWS Lambda, Vercel Functions, or Netlify Functions

📚 See [ARCHITECTURE.md](ARCHITECTURE.md) for detailed migration guides.

---

## ⚙️ Configuration

### Development Mode

CORS is configured for open access during development. To prepare for production:
```javascript
// In Backend/server.js
app.use(cors({
  origin: 'https://yourdomain.com', // Replace with your domain
  credentials: true
}));
```

### Authentication Fallback

If remote auth endpoints are unavailable, the app automatically falls back to local Express endpoints (`/api/login`, `/api/signup`).

---

## 🛠️ Troubleshooting

<details>
<summary><strong>Port already in use</strong></summary>
```bash
# Kill process on port 3000
npx kill-port 3000
npm start
```
</details>

<details>
<summary><strong>Authentication not working</strong></summary>

1. Check that the backend server is running
2. Verify CORS settings in `Backend/server.js`
3. Check browser console for error messages
</details>

<details>
<summary><strong>Data not saving</strong></summary>

Ensure `sessionStorage` is enabled in your browser and not in private/incognito mode.
</details>

---

## 👥 Team

<table>
<tr>
<td align="center">
<strong>🌐 Tap to Build (Web Platform)</strong><br>
Built by <a href="#">[Your Name]</a> & <a href="#">[Friend's Name]</a>
</td>
</tr>
<tr>
<td align="center">
<strong>📱 Refqa (Mobile App)</strong><br>
Built by <a href="#">[Colleague 1]</a>, <a href="#">[Colleague 2]</a>, <a href="#">[Colleague 3]</a>
</td>
</tr>
</table>

---

## 🙏 Acknowledgments

Special thanks to:
- Our advisors and professors
- The entire graduation project team
- Everyone who supported us throughout this journey

---

<div align="center">

### ⭐ If you like this project, please consider giving it a star!

**Made with ❤️ for our graduation project**

[Report Bug](https://github.com/yourusername/tap-to-build/issues) • [Request Feature](https://github.com/yourusername/tap-to-build/issues)

</div>