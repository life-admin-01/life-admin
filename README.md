Life Admin – AI Powered Personal Document Management System

Project Context File for GitHub Copilot

1. Project Overview

Life Admin is a web-based personal document management system that helps users organize, store, and analyze important documents using AI.

Users often store documents such as bills, insurance papers, medical prescriptions, warranty cards, and financial documents in different places. This makes it difficult to track deadlines such as bill payments or document expiration.

The purpose of Life Admin is to provide a centralized platform where users can upload documents and the system automatically extracts useful information using OCR and AI. The system can then generate reminders for important dates.

This project is a student group project and is intended to demonstrate practical implementation of web development, AI integration, and document processing.

---

2. Main Features

The system should support the following core features.

1. User Authentication

Users should be able to create an account and log in securely.

Features:

- Signup
- Login
- Session handling

---

2. Document Upload

Users should be able to upload documents.

Supported formats:

- PDF
- JPG
- PNG

Features:

- Upload document
- Store file
- Save document metadata

---

3. OCR Processing

After a document is uploaded, the system should extract text from it.

Technology:

- Tesseract.js

Process:

1. User uploads document
2. OCR extracts text
3. Extracted text is stored

---

4. AI Document Analysis

After OCR, AI will analyze the extracted text.

Goals:

- Identify document type
- Extract important information
- Detect dates

Example document types:

- Electricity bill
- Insurance document
- Warranty
- Medical prescription
- Bank document

AI APIs (Free):

- HuggingFace API
- Groq API

Expected Output Format:

{
 documentType: "Electricity Bill",
 importantDates: ["2026-05-15"],
 keyInformation: {
    provider: "Electric Company",
    amount: "₹1200"
 }
}

---

5. Reminder System

If important dates are detected, the system should create reminders.

Examples:

- Bill payment reminder
- Insurance renewal
- Warranty expiration

Reminder Features:

- Store reminder
- Show upcoming reminders on dashboard

---

6. Dashboard

The dashboard should display:

- Uploaded documents
- Document categories
- Upcoming reminders
- Quick search

---

3. Technology Stack

Frontend

- Next.js
- React
- Tailwind CSS

Backend

- Next.js API Routes

Database

- MongoDB

OCR

- Tesseract.js

AI APIs

- HuggingFace API
- Groq API

---

4. Project Folder Structure

The project should follow a clear modular structure.

life-admin/

app/
  page.tsx
  dashboard/
      page.tsx
  upload/
      page.tsx
  documents/
      page.tsx

components/
  Navbar.tsx
  UploadForm.tsx
  DocumentCard.tsx
  ReminderCard.tsx
  SearchBar.tsx

lib/
  mongodb.ts
  aiService.ts
  ocrService.ts

models/
  User.ts
  Document.ts
  Reminder.ts

pages/api/
  upload.ts
  analyze.ts
  documents.ts
  reminders.ts

utils/
  extractDates.ts
  documentClassifier.ts

---

5. Database Schema

User

Fields:

- id
- name
- email
- password
- createdAt

---

Document

Fields:

- id
- userId
- fileUrl
- extractedText
- documentType
- extractedDates
- createdAt

---

Reminder

Fields:

- id
- userId
- documentId
- reminderDate
- message
- status

---

6. System Workflow

1. User logs into the system
2. User uploads a document
3. OCR extracts text from the document
4. AI analyzes the text
5. Important information and dates are extracted
6. Data is stored in the database
7. Reminders are created if important dates exist
8. Dashboard displays documents and reminders

---

7. Coding Guidelines

When generating code:

- Use clean and modular architecture
- Follow React best practices
- Use async functions for API calls
- Handle errors properly
- Write reusable components
- Maintain separation between UI, services, and database logic

---

8. Testing Guidelines

For every module:

- Validate user input
- Test API endpoints
- Test OCR output
- Test AI response parsing
- Test reminder creation

Unit tests should be written where possible.

---

9. Copilot Assistance Instructions

Copilot should help with the following tasks:

- Generating React components
- Creating API endpoints
- Implementing OCR processing
- Integrating AI APIs
- Writing database queries
- Suggesting performance improvements
- Writing unit tests
- Reviewing and refactoring code

At the end of each task, Copilot should review the code and suggest improvements for:

- performance
- security
- error handling
- code readability
- testing
