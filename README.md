# Important Flowers - Publication Schedule Overview

A sophisticated publication timeline application with drag-and-drop functionality, real-time updates, and book cover management.

## Features

- 📅 **Interactive Timeline**: Drag-and-drop book positioning
- 📚 **Book Management**: Add, edit, and delete books
- 🖼️ **Cover Options**: Upload images, use URLs, or create text covers
- 📝 **Private Notes**: Personal notes for each book
- 🔍 **Zoom Controls**: Adjust timeline view
- ☁️ **Real-time Sync**: Firebase-powered live updates

## Deployment

### Render.com Deployment

1. **Connect your repository** to Render.com
2. **Create a new Static Site** service
3. **Configure settings**:
   - **Build Command**: `echo "Static site - no build needed"`
   - **Publish Directory**: `.` (root)
   - **Root Directory**: Leave empty
4. **Deploy** - Render will automatically serve your HTML file

### Environment Variables

No environment variables needed - Firebase configuration is included in the HTML file.

## Development

```bash
# Start local development server
python3 -m http.server 8001
# or
npx serve .
```

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Tailwind CSS
- **Backend**: Firebase (Firestore, Storage, Auth)
- **Deployment**: Render.com Static Sites

## File Structure

```
Important Flowers/
├── ImportantFlowers.html    # Main application
├── static/                  # Static assets
│   ├── ImpFlowers.png      # Logo
│   └── favicon (1).ico     # Favicon
├── render.yaml             # Render deployment config
├── package.json            # Project metadata
└── README.md              # This file
``` 