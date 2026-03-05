# Microsoft Custom Navigation Menu

A customizable hierarchical navigation component for SharePoint and other web applications. Supports view/edit modes, drag & drop, and persistent storage.

## Preview

<img width="374" height="367" alt="Screenshot 2026-03-05 at 12 53 17" src="https://github.com/user-attachments/assets/329de45c-019a-4c26-a245-f00ab79e0305" />

<img width="377" height="599" alt="Screenshot 2026-03-05 at 12 53 33" src="https://github.com/user-attachments/assets/a870f8c4-3917-4346-8806-c4e28c9f98e4" />

<img width="226" height="283" alt="Screenshot 2026-03-05 at 12 53 45" src="https://github.com/user-attachments/assets/44f5e92d-7f85-4936-b331-a4e815e175da" />

<img width="465" height="454" alt="Screenshot 2026-03-05 at 12 53 53" src="https://github.com/user-attachments/assets/83e00f53-0f99-412a-801b-82f7925e840f" />

## ✨ Features

### 👁️ View Mode
- Hierarchical navigation with expandable/collapsible sections
- Automatic current page highlighting
- Parent item highlighting for active child pages
- Smooth chevron animations
- Responsive design
- Support for both links and text labels
- Open in new tab functionality

### ✏️ Edit Mode
- Full CRUD operations on navigation items
- Drag & drop reordering
- Context menu with actions:
  - Edit item
  - Move up/down
  - Make sub link / Promote
  - Add sub link
  - Remove item
- Visual drop indicators (before/after/child)
- Add root-level links
- Save/Cancel changes

### 🎨 UI/UX
- Clean, modern interface inspired by SharePoint design
- Context menus positioned relative to buttons
- Modal dialog for adding/editing links
- Form validation
- Persistent state (localStorage)
- Mobile-friendly

## 🚀 Installation

1. Include the CSS (optional - you can use the embedded styles):

```html
<link rel="stylesheet" href="path/to/your/general.css">
```

2. Copy the entire HTML/CSS/JavaScript code from `text.html` into your page (e.g. SharePoint Embed web part or Script Editor).

3. The navigation will automatically initialize.

## 📋 Usage

### Basic Structure
The component creates a navigation container with two modes:
- **View mode:** Regular navigation for site visitors
- **Edit mode:** Management interface for administrators

### Data Persistence
- Navigation structure is stored in **localStorage** (key: `customNavData`)
- Expanded/collapsed states are saved (key: `customNavExpanded`)

### Default Data
If no saved data exists, the component creates sample links:
- Home
- Documents
- Pages
- Site contents

## 🛠️ API

### Methods
| Method | Description |
|--------|-------------|
| `toggleEditMode()` | Switch between view/edit modes |
| `saveAndExitEdit()` | Save changes and return to view mode |
| `cancelEdit()` | Discard changes and return to view mode |
| `addRootLink()` | Open dialog to add new root-level link |
| `addSubLink(parentId)` | Add child link to specified parent |
| `editItem(id)` | Edit existing navigation item |
| `deleteItem(id)` | Remove item after confirmation |
| `moveUp(id)` / `moveDown(id)` | Reorder items |
| `promoteSubLink(id)` | Move item up one level |
| `demoteToSubLink(id)` | Make item a child of previous sibling |

### Data Structure
```javascript
{
  id: "unique-id",           // Auto-generated
  title: "Link Text",        // Display name
  url: "https://...",        // URL (for links)
  type: "link" | "text",     // Item type
  openInNewTab: true/false,  // Target _blank
  children: []               // Nested items
}
```

## 🎯 Customization

### Styling
The component uses CSS classes that can be overridden:
- `.nav-header` - Header bar
- `.nav-item-content` - Individual menu items
- `.active-link` / `.active-parent` - Current page highlighting
- `.edit-btn` - Mode toggle button
- `.dialog-content` - Modal dialog

### Behavior
You can modify:
- Default navigation items in `loadData()`
- URL matching logic in `getPath()`
- Highlight behavior in `highlightCurrentPage()`
- Drag & drop sensitivity thresholds

## 📱 Browser Support
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- IE11 (with polyfills)

## 🔧 Technical Details
- **Pure JavaScript** - No dependencies
- **LocalStorage** - Client-side persistence
- **CSS Grid/Flexbox** - Modern layouts
- **Event Delegation** - Efficient event handling
- **MutationObserver** - DOM change detection
- **Drag & Drop API** - Native HTML5 drag & drop

## 🤝 Contributing
Feel free to submit issues and enhancement requests!

## 📄 License
MIT License - feel free to use in personal and commercial projects.

---

*Note: This component was originally built for SharePoint but works in any environment with minimal adaptation. The embedded CSS ensures it looks great even without the external stylesheet.*
