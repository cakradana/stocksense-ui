# StockSense UI

A custom component registry built on [shadcn/ui](https://ui.shadcn.com) for StockSense projects.

## 🚀 Quick Start

### Setting Up the Registry

1. **Install dependencies**:

```bash
npm install
```

2. **Build the registry**:

```bash
npm run registry:build
```

This generates the registry JSON files in the `public/r` directory.

3. **Serve the registry locally**:

```bash
npm run dev
```

The registry will be available at `http://localhost:3001/r/[NAME].json`.

### Using Components in Your Project

1. **Install components** from this registry:

```bash
# Local development
npx shadcn@latest add http://localhost:3001/r/button.json

# Or from published URL
npx shadcn@latest add https://your-domain.com/r/button.json
```

## 📦 Available Components

- **Button** - Versatile button component with multiple variants

_More components coming soon!_

## 🎨 Customization

All components in this registry follow the StockSense design system and can be customized to match your specific needs.

### Theming

Components use CSS variables for theming. You can customize the theme by modifying the values in your project's CSS file:

```css
@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 84% 4.9%;
    /* ... other variables */
  }
}
```

## 🛠️ Development

### Adding New Components

1. Create the component file in `registry/ui/[component-name].tsx`
2. Create the component config in `registry/ui/[component-name].json`
3. Update the registry index if needed
4. Commit and push to GitHub

### Component Structure

Each component requires:

- **Component file** (`.tsx`) - The actual React component
- **Config file** (`.json`) - Metadata including dependencies

Example config structure:

```json
{
  "name": "component-name",
  "type": "registry:ui",
  "dependencies": ["package-name"],
  "registryDependencies": ["other-component"],
  "files": [
    {
      "path": "ui/component-name.tsx",
      "type": "registry:ui"
    }
  ]
}
```

## 🔗 Usage in Projects

This registry works with:

- ✅ Vite + React
- ✅ Next.js (App Router & Pages Router)
- ✅ Remix
- ✅ Any React-based framework

## 📝 License

Built for StockSense projects by unifluxid.

## 🤝 Contributing

This is a private registry for StockSense projects. If you're part of the team and want to add components, please follow the development guidelines above.

---

**Note:** Make sure your project has the required dependencies installed:

- `tailwindcss`
- `class-variance-authority`
- `clsx`
- `tailwind-merge`
