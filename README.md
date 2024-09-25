# Tauri React Template

A robust and feature-rich template for building desktop applications with Tauri, React, Vite, TypeScript, Tailwind CSS, React Query, and ShadCN.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Available Scripts](#available-scripts)
- [Project Structure](#project-structure)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Features

- Tauri Integration: Build secure and lightweight desktop applications.
- React 18: Modern and efficient UI library.
- Vite: Fast and optimized development build tool.
- TypeScript: Strongly typed JavaScript for better developer experience.
- Tailwind CSS: Utility-first CSS framework for rapid UI development.
- React Query: Data fetching and state management.
- ShadCN UI: Accessible and customizable UI components.
- Routing: Client-side routing with React Router DOM.
- Icons: Rich icon library with Radix UI and Lucide React.
- State Management: Simple and scalable state management with React hooks.
- Build Scripts: Streamlined scripts for development and production builds.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Node.js: Install Node.js (v16 or higher).
- Rust: Install Rust (required for Tauri).
- Tauri CLI: Install Tauri CLI globally:
  ```bash
  npm install -g @tauri-apps/cli
  ```

## Installation

1. Clone the Repository

   ```bash
   git clone https://github.com/your-username/tauri_template.git
   cd tauri_template
   ```

2. Install Dependencies

   ```bash
   npm install
   ```

3. Initialize Tauri

   If this is not already set up, initialize Tauri in your project:

   ```bash
   tauri init
   ```

## Available Scripts

In the project directory, you can run:

- `npm run dev`: Runs the application in development mode using Vite.
- `npm run build`: Compiles the TypeScript code and builds the application for production.
- `npm run preview`: Locally preview the production build.
- `npm run tauri`: Runs Tauri commands. You can pass additional arguments as needed.
- `npm run tauri:dev`: Runs the application in development mode with Tauri.
- `npm run tauri:build`: Builds the application for production with Tauri.

## Project Structure

```
tauri_template/
├── src/
│   ├── components/
│   │   └── ui/
│   │       └── Button.tsx
│   ├── screens/
│   │   └── Index.tsx
│   ├── App.tsx
│   ├── main.tsx
│   └── index.css
├── tauri/
│   └── ... (Tauri configuration and source files)
├── package.json
├── tsconfig.json
├── vite.config.ts
├── tailwind.config.js
├── postcss.config.js
└── README.md
```

## Customization

### Adding New Routes

1. Create a New Screen

   ```tsx
   // src/screens/About.tsx
   import React from "react";

   export function About() {
     return <div className="p-4">About Page</div>;
   }
   ```

2. Update Routing

   ```tsx
   // src/App.tsx
   import { HashRouter as Router, Routes, Route } from "react-router-dom";
   import { Index } from "./screens/index";
   import { About } from "./screens/About";

   function App() {
     return (
       <Router>
         <Routes>
           <Route path="/" element={<Index />} />
           <Route path="/about" element={<About />} />
         </Routes>
       </Router>
     );
   }

   export default App;
   ```

### Styling with Tailwind CSS

Customize the Tailwind configuration in `tailwind.config.js` to extend themes, add plugins, or modify existing styles.

```javascript
// tailwind.config.js
module.exports = {
  content: ["./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      // Customizations here
    },
  },
  plugins: [
    require("tailwindcss-animate"),
    // Add other plugins here
  ],
};
```

### Using React Query

Set up a QueryClient and provide it to your application.

```tsx
// src/main.tsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "../index.css";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

const queryClient = new QueryClient();

ReactDOM.createRoot(document.getElementById("root") as HTMLElement).render(
  <React.StrictMode>
    <QueryClientProvider client={queryClient}>
      <App />
    </QueryClientProvider>
  </React.StrictMode>
);
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the Repository
2. Create a New Branch
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Commit Your Changes
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to the Branch
   ```bash
   git push origin feature/YourFeature
   ```
5. Open a Pull Request
