# /setup — React + Vite + TypeScript + Tailwind CSS Project Setup

Ask for the project name if not provided in `$ARGUMENTS`, then run the following steps in order.

## Step 1: Get Project Name
Use `$ARGUMENTS` as the project name if provided. Otherwise, ask the user: "What is your project name?"

## Step 2: Create Project and Install Dependencies

```bash
npm create vite@latest <project-name> -- --template react-ts
cd <project-name>
npm install
npm install -D tailwindcss @tailwindcss/vite
```

## Step 3: Overwrite vite.config.ts

```bash
cat > vite.config.ts << 'EOF'
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
})
EOF
```

## Step 4: Overwrite src/index.css

```bash
cat > src/index.css << 'EOF'
@import "tailwindcss";
EOF
```

## Step 5: Create CLAUDE.md

```bash
cat > CLAUDE.md << 'EOF'
# CLAUDE.md

## Stack
- React 18 + Vite + TypeScript + Tailwind CSS v4

## Commands
- `npm run dev`   — Start dev server
- `npm run build` — Production build
EOF
```

## Step 6: Print Completion Message

```
✅ <project-name> is ready!
→ cd <project-name> && npm run dev
```