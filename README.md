# Book Store — Frontend

An Angular 17 single-page application for managing a personal book catalog. It communicates with a .NET Web API backend to perform full CRUD operations on books.

---

## Features

- **Landing page** — Overview of the application with quick-access navigation
- **Book Catalog** — View all books in a clean, sortable table with delete support
- **Add a Book** — Reactive form to create a new book entry (Title, Author, ISBN, Publication Date)
- **Edit a Book** — Pre-populated form to update an existing book's details
- **Toast notifications** — Real-time success/error feedback via `ngx-toastr`

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Angular 17 |
| Styling | Bootstrap 5.3, Bootstrap Icons 1.11 |
| HTTP | Angular `HttpClient` |
| Forms | Angular Reactive Forms |
| Notifications | ngx-toastr 18 |

---

## Prerequisites

- **Node.js** v18+ and **npm**
- **Angular CLI** v17  
  ```bash
  npm install -g @angular/cli@17
  ```
- **BookStore API** (.NET 8) running locally at `https://localhost:7219`

---

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Configure the API URL

The backend API URL is set in `src/environments/environment.ts`:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://localhost:7219/api/books'
};
```

Update this value if your backend runs on a different host or port.

### 3. Start the development server

```bash
ng serve
```

Navigate to `http://localhost:4200/`. The application will automatically reload when source files change.

---

## Application Routes

| Path | Page | Description |
|---|---|---|
| `/` | Landing | Home / welcome page |
| `/books` | Catalog | Full list of all books |
| `/books/add` | Add Book | Form to create a new book |
| `/books/edit/:id` | Edit Book | Form to update an existing book |

---

## Book Model

Each book record contains the following fields:

| Field | Type | Validation |
|---|---|---|
| `title` | string | Required, min 2 characters |
| `author` | string | Required |
| `isbn` | string | Required, 10 or 13 digits |
| `publicationDate` | string (date) | Required |

---

## Available Scripts

| Command | Description |
|---|---|
| `ng serve` | Start the local development server at `http://localhost:4200` |
| `ng build` | Build the production bundle into the `dist/` directory |
| `ng test` | Run unit tests via Karma |
| `ng generate component <name>` | Scaffold a new component |

---

## Project Structure

```
src/
├── app/
│   ├── features/
│   │   ├── components/
│   │   │   ├── landing/          # Landing page
│   │   │   ├── book-list/        # Book catalog table
│   │   │   ├── book-create/      # Add new book page
│   │   │   ├── book-edit/        # Edit book page
│   │   │   └── book-form/        # Shared reactive form component
│   │   └── service/
│   │       └── book.service.ts   # HTTP service for Book API
│   ├── app-routing.module.ts     # Route definitions
│   └── app.module.ts             # Root module
├── environments/
│   ├── environment.ts            # Production environment (API URL)
│   └── environment.development.ts
└── styles.css                    # Global styles
```


# 📚 Book Management API

A simple RESTful Web API built using **ASP.NET Core (.NET 8 LTS)** for managing books.  
This API supports full CRUD operations and follows clean architecture principles using Controllers, Services, Repositories, and DTOs.

---

## 🚀 Tech Stack

- .NET 8 (LTS)
- ASP.NET Core Web API
- C#
- RESTful API Design
- In-Memory Data Storage
- DTO Pattern
- Repository & Service Pattern

---

## 📂 Project Structure

```
BookManagementAPI/
│
├── Controllers/
├── DTOs/
├── Models/
├── Repositories/
│   └── Interfaces/
├── Services/
│   └── Interfaces/
├── Program.cs
├── appsettings.json
└── BookManagementAPI.csproj
```

---

## 📌 Features

- Create a Book
- Get All Books
- Get Book by ID
- Update Book
- Delete Book
- Server-side validation using Data Annotations
- DTO-based request & response handling
- Clean layered architecture

---

## 📘 Book Model

| Property | Type |
|----------|------|
| Id | int |
| Title | string |
| Author | string |
| Isbn | string |
| PublicationDate | DateTime |

---

## 🔗 API Endpoints

### Get All Books
```
GET /api/books
```

### Get Book By ID
```
GET /api/books/{id}
```

### Create Book
```
POST /api/books
```

### Update Book
```
PUT /api/books/{id}
```

### Delete Book
```
DELETE /api/books/{id}
```

---

## 🛠 How to Run the Backend

### 1️⃣ Install .NET 8 SDK  
Download from:  
https://dotnet.microsoft.com/download

### 2️⃣ Clone the repository
```bash
git clone <your-backend-repo-url>
cd BookManagementAPI
```

### 3️⃣ Restore dependencies
```bash
dotnet restore
```

### 4️⃣ Run the project
```bash
dotnet run
```

---

## 🧪 Testing the API

You can test using:

- Swagger UI (if enabled)
- Postman
- The included `.http` file
- Angular frontend

---

## 🏗 Architecture Overview

This project follows a layered architecture:

Controller → Service → Repository → In-Memory Data

DTOs are used to:
- Prevent over-posting
- Protect domain models
- Control API contracts
- Improve security

---

## 🔒 Validation

- Server-side validation using Data Annotations
- ModelState validation enabled via `[ApiController]`

---

## 📌 Notes

- Data is stored in-memory (no database used as per assignment requirement).
- This project is built using .NET 8 (LTS) for long-term stability and performance.

---

## 👨‍💻 Author

Developed as part of a Software Engineer technical assignment.

---

## Further Help

For Angular CLI usage, run `ng help` or visit the [Angular CLI documentation](https://angular.io/cli).
