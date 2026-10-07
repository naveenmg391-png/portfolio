# Personal Portfolio Website

A complete full-stack personal portfolio project matching the internship/task requirements:

- Frontend: HTML, CSS and JavaScript
- Backend: Node.js + Express.js
- Database: MongoDB + Mongoose
- REST API for portfolio projects and contact messages
- Responsive design
- Project filtering
- Contact form
- Simple admin API for adding, updating and deleting projects
- Ready for deployment to services such as Render/Railway/Vercel/Netlify

## 1. Requirements

Install:

1. Node.js 18+
2. MongoDB Community Server OR a MongoDB Atlas account
3. VS Code

## 2. Setup

Open this folder in VS Code.

In the terminal:

```bash
npm install
```

Create a `.env` file in the project root:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/portfolio_db
```

If you use MongoDB Atlas, replace `MONGODB_URI` with your Atlas connection string.

## 3. Run

```bash
npm run dev
```

Then open:

http://localhost:5000

The server also exposes the API at:

http://localhost:5000/api/projects

## 4. Add your details

Open:

`frontend/index.html`

Replace the sample name, email, GitHub and LinkedIn links.

Open:

`frontend/js/app.js`

The sample projects are loaded from MongoDB. If the database is empty, the application automatically creates sample projects on first server start.

## 5. API endpoints

### Projects

GET all projects:

```http
GET /api/projects
```

GET one project:

```http
GET /api/projects/:id
```

POST a project:

```http
POST /api/projects
Content-Type: application/json

{
  "title": "My Project",
  "description": "Project description",
  "technologies": ["HTML", "CSS", "JavaScript"],
  "category": "Web",
  "githubUrl": "https://github.com/yourname/project",
  "liveUrl": "https://example.com",
  "image": "https://images.unsplash.com/..."
}
```

PUT a project:

```http
PUT /api/projects/:id
```

DELETE a project:

```http
DELETE /api/projects/:id
```

### Contact

POST:

```http
POST /api/contact
Content-Type: application/json

{
  "name": "Student",
  "email": "student@example.com",
  "message": "Hello!"
}
```

## 6. Project structure

```text
personal-portfolio-fullstack/
│
├── backend/
│   ├── models/
│   │   ├── Project.js
│   │   └── Message.js
│   ├── routes/
│   │   ├── projects.js
│   │   └── contact.js
│   ├── seed.js
│   └── server.js
│
├── frontend/
│   ├── index.html
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── app.js
│
├── .env.example
├── .gitignore
├── package.json
└── README.md
```

## 7. Deployment

### Backend

Deploy the repository to Render or Railway.

Build command:

```bash
npm install
```

Start command:

```bash
npm start
```

Set these environment variables:

```text
PORT=5000
MONGODB_URI=your_mongodb_atlas_connection_string
```

### Frontend

This version serves the frontend from Express, so you can deploy the whole project as one Node.js service.

For a separate frontend deployment, change the API base URL in:

`frontend/js/app.js`

from:

```js
const API_BASE = "/api";
```

to your deployed backend URL, for example:

```js
const API_BASE = "https://your-backend.onrender.com/api";
```

## 8. Important

Do not upload your `.env` file or MongoDB password to GitHub.

This project is intended as a student portfolio/internship submission and can be customized with your own name, skills, certificates and projects.
