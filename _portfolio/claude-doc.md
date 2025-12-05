---
layout: single
title: "Build a Notes App with Claude Code"
permalink: /claude-code/overview/
classes: wide            
sidebar:
  nav: claude_code
author_profile: false
toc: true
toc_sticky: true

---

This tutorial walks you through creating a Notes application that lets users create, view, edit, and delete notes. You’ll generate the backend, frontend, database, tests, and final refinements entirely through iterative prompts using Claude Code.

## What You’ll Build
A simple Notes app consists of several key parts working together. The backend (server) handles storing and managing notes, while the database keeps all your notes safe. The frontend (UI) is what users see and interact with, allowing them to view, add, edit, or delete notes. The app uses CRUD functionality which is create, read, update, and delete to manage these actions. Unit tests ensure that everything works correctly. Upon completing this tutorial you'll have created a digital notebook where you can write new notes, view existing ones, make changes, or remove notes whenever needed.

## Prerequisites
<ul>
<li>Claude Code access</li>
<li>Basic understanding of Python and JavaScript</li>
<li>Git installed (optional but recommended)</li>
</ul>

## Create the project with Claude Code
Step 1: Start a new workspace. In Claude Code navigate to <b>Claude</b> -> <b>Code</b> -> <b>New Workspace</b>.
Step 2: Give high-level instructions.

```sql
Create a full stack “Notes App” with:
- FastAPI backend using SQLite
- A Notes model: id, title, content, created_at
- CRUD endpoints
- React frontend with pages for listing, creating, and editing notes
- Clean folder structure for client and server
Add placeholder text where needed. Generate minimal but working code.
```
Claude Code creates folders and files for the backend and frontend automatically, like a starter project.
```css
backend/
  main.py
  database.py
  models.py
  routers/notes.py
frontend/
  src/App.jsx
  src/components/...
  package.json
```
Step 3: Review the generated file structutre and apply all generated files.

## Build the backend CRUD API
Step 1: Open `backend/routers/notes.py`.

Step 2: Ask Claude Code to create routes which are API endpoints for notes. 
```bash
Implement all CRUD routes for the Notes model:
- GET /notes
- GET /notes/{id}
- POST /notes
- PUT /notes/{id}
- DELETE /notes/{id}

Use Python and SQLite
```
Step 3: Review what Claude Code generated and apply the changes. Ensure that all endpoints follow the same response style and validation errors are handled correctly.  

## Build the frontend
Step 1: Open `frontend/src/App.jsx`.

Step 2: Prompt Claude Code.
```sql
Create a simple UI to:
- List notes --Shows all saved notes
- Add a new note
- Edit and delete notes
Connect it to the backend using fetch() --fetch() allows frontend to talk to backend
```
Step 3: Claude Code may also generate components like `NotesList.jsx` or `NoteEditor.jsx`. Apply the changes.

## Connect frontend and backend
Step 1: Ask Claude Code to create an API utility file `api.js` with these functions.
```scss
getNotes(), getNote(id), createNote(), updateNote(), deleteNote()
```
Step 2: Link these functions in your React components so the app can display real data from the backend. 
The frontend talks to http://localhost:8000 by default.

## (Optional) Add styling
Ask Claude Code to add simple CSS styling. This makes the Notes app visually clean and easier to use.
```diff
Add simple CSS styling:
- Clear spacing
- Easy to read layout
- Minimal colors
```

## Add unit tests
Before you launch the app to production run a few tests. This is to ensure that the backend logic of the Notes App works correctly. 
```diff
Create simple pytest unit tests for backend:
- Test creating a note
- Test reading notes
- Test editing a note
- Test deleting a note
Use a temporary SQLite database for testing
```

## Run your Notes App locally
Step 1: Start the backend. 
```lua
uvicorn backend.main:app --reload
```
Step 2: Start the frontend.
```powershell
npm install
npm start
```
Step 3: Open your browser: http://localhost:3000

Congratulations! You should see your Notes App working. You can now add, view, edit, and delete notes. 
