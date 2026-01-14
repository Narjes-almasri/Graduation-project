<div align="center">

# 🚀 Tap to Build

<!-- ### *Master Web Development Through Hands-On Practice* -->

<img src="Frontend/assets/output.gif" width="700" alt="Tap to Build Demo">

[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)

[Features](#-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Deployment](#-deployment)

---

</div>

## 📖 About

**Tap to Build** is the practical training platform of the **Refqa** ecosystem—where learning meets real-world application. After mastering web development concepts through Refqa's educational features, users transition here to apply their knowledge by building real landing pages for small businesses.

This hands-on approach bridges the gap between theory and practice, allowing learners to create professional web projects while reinforcing core web development concepts.

> 🎓 **Graduation Project**  
> **Refqa** is our comprehensive educational platform graduation project consisting of two integrated components:
> 
> ### 📱 **Refqa Mobile App** - *The Learning Hub*
> An educational platform featuring:
> - 🎯 Interactive learning paths & completions
> - 🏆 Ranking system & gamification
> - 👥 Community features - connect with fellow learners
> - 🌍 Build your learning society
> - 🔗 Seamless navigation to Tap to Build (integration in progress)
> 
> **Built by:** [@Amr-alali](https://github.com/AmrHAlali)
> 
> ### 🌐 **Tap to Build** - *The Training Ground*
> A web platform for learning core web concepts and understanding page structure. Through the website, users can design GUIs in a modern and smooth way without prior experience,
follow clear step-by-step flows to learn the core components of any page, choose a color palette with a handy tool, design their own logo, understand the main sections of a page, and >enter their data to produce a complete website. An Admin Evaluation option provides feedback on areas for improvement.
> 
> **Built by:** [@Narjes-almasri](https://github.com/Narjes-almasri) & [@leen-almahthi](https://github.com/LeenAlmahthi)
> 
> ### 🔧 **Backend Infrastructure**
> Unified database and API services powering both platforms.
> 
> **Built by:** [Mahmoud-zabout]

---

## 🎯 Purpose & Vision

**Tap to Build** serves as the practical training extension of Refqa's educational experience:

1. **📚 Learn** core web concepts in the Refqa mobile app
2. **🛠️ Practice** by building real projects in Tap to Build
3. **🎓 Master** web development through hands-on experience

This creates a complete learning-to-earning pipeline for aspiring web developers.

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎨 **Hands-On Builder**
- Step-by-step guided workflow
- Real-time preview as you build
<!-- - Apply concepts learned in Refqa -->
- No-code friendly interface

### 🔐 **Secure Platform**
- Bcrypt password hashing
- Session management
<!-- - Integrated with Refqa ecosystem -->

</td>
<td width="50%">

### 🎯 **Complete Customization**
- Color palette selection
- Logo creation & upload
- Content editing tools
- Professional templates

### 📊 **Progress Tracking**
- Site management dashboard
- Project evaluation system
- Learning analytics (via Refqa)

</td>
</tr>
</table>

---

## 🎬 See It In Action

<div align="center">
<img src="Frontend/assets/output2.gif" width="700" alt="Final Result Showcase">

*From learning concepts to building real websites*

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
<!-- 
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

📚 See [ARCHITECTURE.md](ARCHITECTURE.md) for detailed migration guides. -->

<!-- --- -->

<!-- ## ⚙️ Configuration

### Development Mode

CORS is configured for open access during development. To prepare for production:

```javascript
// In Backend/server.js
app.use(cors({
  origin: 'https://yourdomain.com', // Replace with your domain
  credentials: true
}));
``` -->

<!-- ### Authentication Fallback

If remote auth endpoints are unavailable, the app automatically falls back to local Express endpoints (`/api/login`, `/api/signup`). -->

---

## 🔄 Integration with Refqa

> **Note:** Navigation from the Refqa mobile app to Tap to Build is currently in development. Once complete, users will be able to seamlessly transition from learning modules to practical projects.

**Planned Features:**
- Single sign-on between platforms
- Progress synchronization
- Unified learning path tracking
- Achievement system integration

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

<div align="center">

### 🎓 Graduation Project Contributors

</div>

<table>
<tr>
<td align="center" width="33%">
<br>
<strong>📱 Refqa Mobile App</strong><br><br>
<em>Educational Platform Development</em><br>
<sub>Learning paths, rankings, community features</sub><br><br>
👤 <a href="https://github.com/AmrHAlali"><strong>Amr Alali</strong></a>
<br><br>
</td>
<td align="center" width="33%">
<br>
<strong>🌐 Tap to Build</strong><br><br>
<em>Web Training Platform</em><br>
<sub>Hands-on builder, templates, live preview</sub><br><br>
👥 <a href="https://github.com/Narjes-almasri"><strong>Narjes Almasri</strong></a> & <a href="https://github.com/LeenAlmahthi"><strong>Leen Almahthi</strong></a>
<br><br>
</td>
<td align="center" width="33%">
<br>
<strong>🔧 Backend Infrastructure</strong><br><br>
<em>Database & API Development</em><br>
<sub>Unified backend for both platforms</sub><br><br>
👤 <a href="https://github.com/."><strong>Mahmoud-zabout</strong></a>
<br><br>
</td>
</tr>
</table>

---

## 🗺️ Project Roadmap

- [x] Core builder functionality
- [x] Authentication system
- [x] Admin dashboard
- [x] Schema validation
- [ ] Full Refqa app integration
- [ ] Single sign-on implementation
- [ ] Advanced template library
- [ ] Deployment automation
- [ ] Multi-language support

---

<div align="center">

### ⭐ If you like this project, please consider giving it a star!

**Made with ❤️ as part of the Refqa educational ecosystem**

*Empowering learners to become creators*

[Report Bug](https://github.com/Narjes-almasri/finaaal-/issues) • [Request Feature](https://github.com/Narjes-almasri/finaaal-/issues)

</div>
