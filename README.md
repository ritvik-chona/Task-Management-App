# 📋 Advanced Task Manager

## Description
A fully functional, feature-rich task management web application built entirely with vanilla JavaScript, HTML5, and CSS3. This application demonstrates advanced DOM manipulation, event-driven programming, state management, and client-side data persistence without using any frontend frameworks.

## Problem Statement
In today's fast-paced world, people juggle multiple responsibilities across work, personal life, and urgent matters. Traditional task lists lack organization and filtering capabilities. This application solves that problem by providing a comprehensive task management system with:
- **Categorization**: Organize tasks by type (Work, Personal, Urgent, Other)
- **Smart Filtering**: View tasks by status or category
- **Real-time Search**: Find tasks instantly
- **Inline Editing**: Modify tasks without complex forms
- **Data Persistence**: Never lose your tasks

## ✨ Features Implemented

### Core Functionality
- ✅ **Add Tasks**: Create new tasks with categories
- ✅ **Edit Tasks**: Inline editing with save/cancel options
- ✅ **Delete Tasks**: Remove tasks with confirmation
- ✅ **Complete Tasks**: Mark tasks as done with visual feedback
- ✅ **Categories**: 4 distinct categories (Work, Personal, Urgent, Other)
- ✅ **LocalStorage**: All data persists across browser sessions

### Advanced Features
- ✅ **Real-time Search**: Filter tasks as you type
- ✅ **Multiple Filters**: View by All, Active, Completed, or Category
- ✅ **Statistics Dashboard**: Real-time stats showing total, active, completed tasks
- ✅ **Category Breakdown**: View task counts per category
- ✅ **Feedback Messages**: Success/error notifications for all actions
- ✅ **Input Validation**: Prevents empty tasks and enforces character limits
- ✅ **Confirmation Dialogs**: Prevents accidental deletions
- ✅ **Audio Feedback**: Sound effects for task completion
- ✅ **Keyboard Shortcuts**: Ctrl/Cmd + K to focus search
- ✅ **Clear All**: Bulk delete with confirmation
- ✅ **Responsive Design**: Works on desktop, tablet, and mobile

## 🔧 DOM Concepts Used

### 1. Dynamic Element Creation
- **createElement()**: Creating task items, buttons, inputs, spans dynamically
- **appendChild()**: Adding elements to the DOM tree
- **remove()**: Removing elements from DOM

```javascript
const li = document.createElement('li');
const checkbox = document.createElement('div');
todoList.appendChild(li);
```

### 2. DOM Manipulation
- **querySelector() / querySelectorAll()**: Selecting elements
- **setAttribute()**: Setting data attributes for task tracking
- **className / classList**: Dynamic class manipulation
- **innerHTML / textContent**: Content updates
- **style property**: Dynamic styling

```javascript
li.setAttribute('data-task-id', task.id);
btn.classList.add('active');
element.style.display = 'block';
```

### 3. Event Handling
- **addEventListener()**: Attaching event listeners
- **Click events**: Buttons, checkboxes, filters
- **Input events**: Real-time search
- **Keypress events**: Enter to submit, Escape to cancel
- **Event delegation**: Efficient event handling for dynamic elements
- **preventDefault()**: Preventing default form behavior

```javascript
addBtn.addEventListener('click', addTask);
searchInput.addEventListener('input', handleSearch);
document.addEventListener('keydown', handleShortcuts);
```

### 4. DOM Traversal
- **querySelector()** within elements: Finding child elements
- **Parent/child relationships**: Navigating DOM tree
- **Data attributes**: Storing and retrieving custom data

```javascript
const contentDiv = listItem.querySelector('.todo-content');
const taskId = element.dataset.taskId;
```

### 5. Conditional Rendering
- **Display control**: show/hide elements based on state
- **Dynamic content**: Different messages for different states
- **Class-based rendering**: Adding/removing classes for visual states

```javascript
if (filteredTasks.length === 0) {
    emptyState.style.display = 'block';
} else {
    emptyState.style.display = 'none';
}
```

### 6. State Management
- **JavaScript Objects/Arrays**: Complex data structures
- **LocalStorage API**: Client-side persistence
- **State updates trigger re-renders**: Reactive UI updates
- **Filter state tracking**: Managing active filters

```javascript
let tasks = [];
let currentFilter = 'all';
localStorage.setItem('tasks', JSON.stringify(tasks));
```

## 🚀 How to Run

1. **Clone or Download** this repository
2. **Open** `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge)
3. **Start using** the application immediately - no installation or build process required!

### File Structure
```
project/
│
├── index.html          # Main HTML structure
├── style.css           # All styling and responsive design
├── script.js           # Complete JavaScript logic
└── README.md          # This file
```

## 💻 Technologies Used

### HTML5
- Semantic markup
- Form elements (input, select)
- Data attributes for state management
- SVG for icons

### CSS3
- **Flexbox**: Layout system for responsive design
- **Grid**: Statistics grid layout
- **Animations**: Fade-in, slide-down, pulse effects
- **Transitions**: Smooth hover effects
- **Media Queries**: Responsive breakpoints
- **Custom Scrollbar**: Styled scrollbar for task list

### Vanilla JavaScript (ES6+)
- **Arrow Functions**: Modern syntax
- **Template Literals**: Dynamic string building
- **Array Methods**: filter(), find(), map(), forEach()
- **LocalStorage API**: Data persistence
- **Web Audio API**: Sound effects
- **Date.now()**: Unique ID generation
- **JSON.stringify/parse()**: Data serialization

## 🛡️ Edge Cases & Error Handling

### Input Validation
- ✅ Empty task prevention with error message
- ✅ Character limit enforcement (200 chars)
- ✅ Trim whitespace from inputs
- ✅ Focus management for better UX

### Error Handling
- ✅ **try-catch blocks** for LocalStorage operations
- ✅ **Graceful fallbacks** if storage fails
- ✅ **Confirmation dialogs** for destructive actions
- ✅ **User feedback** for all operations

### State Management
- ✅ **Edit state tracking** prevents multiple simultaneous edits
- ✅ **Empty state handling** shows appropriate messages
- ✅ **Filter state persistence** during operations
- ✅ **Search state updates** trigger re-renders

## 📊 JavaScript Concepts Demonstrated

### Array Methods
```javascript
// filter() - Create new array with items matching condition
tasks.filter(task => task.done === false)

// find() - Find first matching item
tasks.find(task => task.id === targetId)

// map() - Transform array elements
tasks.map(task => task.text)

// forEach() - Iterate over array
tasks.forEach(task => console.log(task))
```

### Object Manipulation
```javascript
const task = {
    id: Date.now(),
    text: "Buy groceries",
    category: "personal",
    done: false,
    createdAt: new Date().toISOString()
};
```

### LocalStorage Pattern
```javascript
// Save
localStorage.setItem('tasks', JSON.stringify(tasks));

// Load
const tasks = JSON.parse(localStorage.getItem('tasks')) || [];

// Error handling
try {
    localStorage.setItem('tasks', JSON.stringify(tasks));
} catch (error) {
    showFeedback('Error saving tasks', 'error');
}
```

### Event Delegation
```javascript
// Instead of adding listeners to each task
// Add one listener to parent and check target
todoList.addEventListener('click', (e) => {
    if (e.target.classList.contains('delete-btn')) {
        deleteTask(id);
    }
});
```

## 🎯 Key Features for Evaluation

### DOM Manipulation (25 marks)
- Dynamic element creation with createElement()
- Complex DOM updates with appendChild/remove
- Attribute manipulation with setAttribute()
- Inline editing that replaces DOM elements
- Event delegation for dynamic content

### Event Handling (20 marks)
- Multiple event types (click, input, keypress)
- Form submission handling
- Keyboard shortcuts
- Real-time event responses
- Event delegation patterns

### JavaScript Logic (20 marks)
- Array filtering and searching
- State management across operations
- Data transformation and validation
- Helper functions for reusability
- Complex conditional logic

### State Handling (20 marks)
- LocalStorage integration
- State persistence across sessions
- Filter and search state management
- Edit state tracking
- Real-time UI synchronization

### Edge Cases (5 marks)
- Input validation
- Error handling with try-catch
- Confirmation dialogs
- Empty state management
- User feedback system

### UI/UX (10 marks)
- Clean, modern design
- Responsive layout
- Smooth animations
- Clear user feedback
- Intuitive interactions

## 🐛 Known Limitations

- LocalStorage has a 5-10MB limit (sufficient for thousands of tasks)
- No cloud sync - data stored locally only
- No multi-user support
- No task sharing capabilities
- Browser-specific (data doesn't sync across devices)

## 🔮 Future Enhancements

- Due dates and deadline reminders
- Task priorities (High, Medium, Low)
- Drag-and-drop task reordering
- Export tasks to CSV/JSON
- Import tasks from files
- Dark/Light theme toggle
- Recurring tasks
- Task notes/descriptions
- Cloud synchronization
- Multi-user collaboration

## 📸 Screenshots

### Main Interface
![Main interface with tasks](https://via.placeholder.com/800x500?text=Add+Your+Screenshot+Here)

### Filter & Search
![Filtering and searching tasks](https://via.placeholder.com/800x500?text=Add+Your+Screenshot+Here)

### Statistics Dashboard
![Real-time statistics](https://via.placeholder.com/800x500?text=Add+Your+Screenshot+Here)

## 👨‍💻 Developer

**Name**: Ritvik Chona  
**Roll Number**: 25bcs10500  
**Project**: Web Dev II Final Project  
**Submission Date**: January 26, 2026

## 📜 License

This project is created for educational purposes as part of the Web Dev II course final project.

---

**⭐ If you found this project helpful, please give it a star!**
