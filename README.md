# Bud-Hunters

A React-based cannabis strain review tracking application built with TypeScript and Tailwind CSS.

## Features

- 🌿 Track and review cannabis strains
- ⭐ Rate strains with a 5-star system
- 🏷️ Categorize by type (Indica, Sativa, Hybrid)
- 💬 Add detailed reviews and effects
- 🔍 Search functionality
- 💾 Local storage for data persistence

## Deployment

This application is configured for multiple deployment options:

### GitHub Pages (Automatic)

The repository is configured to automatically deploy to GitHub Pages when changes are pushed to the `main` branch.

1. Ensure GitHub Pages is enabled in your repository settings
2. Set the source to "GitHub Actions"
3. Push changes to the `main` branch
4. The app will automatically build and deploy

### Vercel (One-Click)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Trade-Grant/Bud-Hunters3)

Or manually:

1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in the project directory
3. Follow the prompts

### Local Development

1. Clone the repository
   ```bash
   git clone https://github.com/Trade-Grant/Bud-Hunters3.git
   cd Bud-Hunters3
   ```

2. Install dependencies
   ```bash
   npm install
   ```

3. Start the development server
   ```bash
   npm start
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

### Building for Production

```bash
npm run build
```

The build output will be in the `build` directory, ready to be deployed to any static hosting service.

## Technology Stack

- **React 18.2** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling (via inline classes)
- **Lucide React** - Icons
- **Create React App** - Build tooling

## Project Structure

```
Bud-Hunters3/
├── public/           # Static files
│   └── index.html    # HTML entry point
├── src/              # Source code
│   ├── App.tsx       # Main application component
│   └── index.tsx     # React entry point
├── .github/
│   └── workflows/
│       └── static.yml # GitHub Pages deployment workflow
├── package.json      # Dependencies and scripts
├── tsconfig.json     # TypeScript configuration
└── vercel.json       # Vercel deployment configuration
```

## License

This project is open source and available under the MIT License.

## Credits

Created by Samir Mulla