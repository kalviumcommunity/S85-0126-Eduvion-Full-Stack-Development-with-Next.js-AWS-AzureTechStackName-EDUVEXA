# EDUVEXA

**EDUVEXA** is a full-stack educational collaboration platform designed to improve student engagement, project visibility, and team collaboration. It provides dashboards, project management, peer feedback, and role-based access to support accountability and better learning outcomes.

## 🚀 Features

* **Dashboard** — Track engagement, activities, tasks, and project progress.
* **Project Management** — Create projects, manage tasks, and monitor progress.
* **Peer Feedback** — Provide structured reviews, ratings, and comments.
* **Team Management** — Manage users, profiles, and team members.
* **Secure File Uploads** — Upload files directly to AWS S3 using pre-signed URLs.
* **Authentication & Authorization** — JWT-based authentication with role-based access control.
* **Responsive UI** — Modern interface with dark mode and responsive layouts.

## 🛠️ Technology Stack

| Category       | Technologies                                   |
| -------------- | ---------------------------------------------- |
| Frontend       | Next.js 14, React 18, TypeScript, Tailwind CSS |
| Backend        | Next.js API Routes, Node.js                    |
| Database       | PostgreSQL, Prisma ORM                         |
| Authentication | JWT, HTTP-only Cookies, bcrypt                 |
| File Storage   | AWS S3, Pre-signed URLs                        |
| UI             | Custom Components, Lucide React                |
| Testing        | Jest, React Testing Library                    |
| CI/CD          | GitHub Actions                                 |

## 📋 Prerequisites

* Node.js 18+
* PostgreSQL
* npm or Yarn
* AWS S3 account for file uploads

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd EDUVEXA
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env.local` file:

```bash
cp .env.example .env.local
```

Configure the required variables:

```env
DATABASE_URL="postgresql://username:password@localhost:5432/mydb"
JWT_SECRET="your-secret-key"

AWS_ACCESS_KEY_ID="your-access-key"
AWS_SECRET_ACCESS_KEY="your-secret-key"
AWS_REGION="ap-south-1"
AWS_BUCKET_NAME="your-bucket-name"
```

### 4. Set Up the Database

```bash
npx prisma generate
npx prisma migrate dev
npx prisma db seed
```

### 5. Start the Development Server

```bash
npm run dev
```

Open the application at:

```text
http://localhost:3000
```

## 🔐 Test Accounts

After running the database seed:

| Role       | Email                                         | Password    |
| ---------- | --------------------------------------------- | ----------- |
| Student    | [alice@example.com](mailto:alice@example.com) | password123 |
| Instructor | [bob@example.com](mailto:bob@example.com)     | password123 |
| Admin      | [david@example.com](mailto:david@example.com) | password123 |

> These credentials are intended for local development and testing only.

## 📤 File Upload System

EDUVEXA uses **AWS S3 pre-signed URLs** for secure and efficient file uploads.

### Key Capabilities

* Direct client-to-S3 uploads
* Temporary pre-signed URLs
* File type and size validation
* Database metadata tracking
* Project-based file organization

### API Endpoints

| Method | Endpoint      | Purpose                          |
| ------ | ------------- | -------------------------------- |
| POST   | `/api/upload` | Generate a pre-signed upload URL |
| POST   | `/api/files`  | Store file metadata              |
| GET    | `/api/files`  | Retrieve uploaded files          |

For detailed file-upload configuration and API documentation, see [`FILE_UPLOAD_API_GUIDE.md`](FILE_UPLOAD_API_GUIDE.md).

## 🧪 Testing

EDUVEXA uses **Jest** and **React Testing Library** for automated testing.

```bash
# Run tests
npm test

# Watch mode
npm run test:watch

# Generate coverage report
npm run test:coverage
```

The project also supports automated testing through **GitHub Actions**.

## 🔄 Development Workflow

The project follows a feature-based Git workflow:

1. Create a feature branch.
2. Implement and test changes.
3. Commit changes with descriptive messages.
4. Open a pull request for review.
5. Merge approved changes into the main branch.

## 📄 License

This project is intended for educational and development purposes.
