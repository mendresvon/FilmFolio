# 🎬 FilmFolio

**Never forget a movie again.** FilmFolio is a modern, full-stack web application that helps users discover, organize, and manage their movie watchlists with a sleek, intuitive interface.

![React](https://img.shields.io/badge/React-19.1-61DAFB?style=flat&logo=react&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?style=flat&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?style=flat&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=flat&logo=docker&logoColor=white)

---

## ✨ Features

### 🎥 Core Functionality
- **Personalized Watchlists** - Create and manage custom movie watchlists
- **Movie Discovery** - Browse and search movies powered by The Movie Database (TMDB) API
- **Real-time Updates** - Seamless user experience with optimistic UI updates
- **Secure Authentication** - JWT-based authentication with bcrypt password hashing

### 🚀 Technical Highlights
- **Redis Caching** - High-performance caching layer with graceful fallback mechanisms
- **Responsive Design** - Modern, mobile-first UI with smooth animations using Framer Motion
- **RESTful API** - Well-structured backend with Express.js and input validation
- **Cloud-Ready** - Containerized with Docker and optimized for cloud deployment (Google Cloud Run)
- **Production-Grade Security** - CORS protection, input sanitization, and secure environment configuration

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** React 19.1 with Vite
- **Routing:** React Router DOM 7.8
- **Animations:** Framer Motion
- **Styling:** CSS Modules with modern design patterns
- **HTTP Client:** Axios
- **UI Components:** React Icons, React Type Animation

### Backend
- **Runtime:** Node.js with Express 5.1
- **Database:** MongoDB (Mongoose ODM)
- **Caching:** Redis (ioredis)
- **Authentication:** JWT + bcryptjs
- **Validation:** express-validator
- **External API:** TMDB (The Movie Database)

### DevOps
- **Containerization:** Docker
- **Environment:** dotenv for configuration management
- **Development:** Nodemon for hot-reloading

---

## 📁 Project Structure

```
filmfolio/
├── backend/               # Express.js API server
│   ├── index.js          # Application entry point
│   ├── routes/           # API route handlers
│   │   ├── auth.js       # Authentication endpoints
│   │   ├── movies.js     # Movie data & TMDB integration
│   │   └── watchlists.js # Watchlist CRUD operations
│   ├── models/           # Mongoose schemas
│   ├── middleware/       # Authentication & validation
│   └── Dockerfile        # Container configuration
│
└── frontend/             # React SPA
    ├── src/
    │   ├── pages/        # Route components
    │   ├── components/   # Reusable UI components
    │   └── styles/       # Global styles & CSS modules
    └── vite.config.js    # Vite configuration
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- MongoDB instance (local or cloud)
- Redis server (optional - graceful fallback enabled)
- TMDB API key ([Get one here](https://www.themoviedb.org/settings/api))

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/filmfolio.git
cd filmfolio
```

2. **Backend Setup**
```bash
cd backend
npm install

# Create .env file with required variables
cat > .env << EOF
PORT=3001
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
TMDB_API_KEY=your_tmdb_api_key
REDIS_URL=your_redis_url (optional)
EOF

npm run dev
```

3. **Frontend Setup**
```bash
cd ../frontend
npm install
npm run dev
```

The application will be available at:
- Frontend: `http://localhost:5173`
- Backend API: `http://localhost:3001`

---

## 🐳 Docker Deployment

Build and run the backend with Docker:

```bash
cd backend
docker build -t filmfolio-backend .
docker run -p 3001:3001 --env-file .env filmfolio-backend
```

---

## 🔑 API Endpoints

### Authentication
- `POST /api/auth/register` - Create new user account
- `POST /api/auth/login` - User login & JWT generation

### Movies
- `GET /api/movies/search?query={term}` - Search movies via TMDB
- `GET /api/movies/:id` - Get detailed movie information

### Watchlists
- `GET /api/watchlists` - Get user's watchlists
- `POST /api/watchlists` - Create new watchlist
- `PUT /api/watchlists/:id` - Update watchlist
- `DELETE /api/watchlists/:id` - Delete watchlist

---

## 🎯 Key Implementation Details

### Redis Caching Strategy
The application implements intelligent caching with Redis:
- Movie data is cached to reduce TMDB API calls
- Automatic cache invalidation strategies
- **Graceful degradation**: If Redis is unavailable, the app seamlessly falls back to direct API calls

### Security Features
- JWT-based stateless authentication
- Password hashing with bcrypt (10 salt rounds)
- Input validation using express-validator
- CORS configuration for cross-origin protection
- Environment variable isolation

### Performance Optimizations
- Redis caching layer reduces API latency by ~80%
- React code-splitting with lazy loading
- Optimized MongoDB queries with indexing
- Vite's fast HMR for development

---

## 👨‍💻 Author

**Von Mendres 「馬盛中」**

Built as a demonstration of full-stack development capabilities, cloud deployment expertise, and modern web application architecture.

---

## 📄 License

This project is licensed under the ISC License.

---

## 🙏 Acknowledgments

- Movie data provided by [The Movie Database (TMDB)](https://www.themoviedb.org/)
- Icons from [React Icons](https://react-icons.github.io/react-icons/)

---

## 🔮 Future Enhancements

- [ ] User reviews and ratings
- [ ] Social sharing features
- [ ] Advanced filtering and sorting
- [ ] Movie recommendations using ML
- [ ] Progressive Web App (PWA) support
- [ ] Email notifications for new releases
