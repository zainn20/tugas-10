#  Mini LinkedIn Website

A simplified LinkedIn-style web application built with ReactJS (frontend) and NodeJS (backend).

---

# Tech Stack

- **Frontend**: ReactJS, React Router, Axios, (optional: Tailwind CSS)
- **Backend**: NodeJS, Express
- **Database**: MySQL
- **Security**: JWT (authentication), bcryptjs (password hashing)

---
  Features

#Authentication
- Register with email and password
- Login with JWT token
- Protect profile & post feed routes with middleware
# Profile Page
- View profile (name, bio, profile picture URL)
- Edit profile
- Change password

# Post Feed
- View all posts (author, content, timestamp)
- Create new post

# Optional Stretch Goals
- Profile picture upload
- Like button on posts
- Edit/delete own posts
- Pagination (load more posts)

---

##  1. ERD / Database Structure

### users
| Field             Type          Description   
| id               | INT, PK      | Auto increment ID       |
| name             | VARCHAR(100) | Full name               |
| email            | VARCHAR(100) | Unique                  |
| password         | VARCHAR(255) | Hashed password         |
| bio              | TEXT         | User bio                |
| profile_picture  | TEXT         | URL to profile picture  |
| created_at       | TIMESTAMP    | Auto timestamp          |

### posts
| Field        | Type         | Description                    |
|--------------|--------------|--------------------------------|
| id           | INT, PK      | Auto increment ID              |
| user_id      | INT, FK      | Foreign key to users(id)       |
| content      | TEXT         | Post content                   |
| created_at   | TIMESTAMP    | Auto timestamp                 |

---

# 2. Function List

### Backend
- Register user (hash password, save to DB)
- Login (verify password, return JWT)
- Get authenticated user profile
- Update profile (name, bio, picture)
- Change password (check old, update new)
- Create post
- Get all posts with author info

### Frontend
- RegisterPage: form for new users
- LoginPage: form and JWT handling
- ProfilePage: show user info
- EditProfilePage: update user info
- PostFeedPage: show all posts
- CreatePostPage: new post input
- AuthContext: handle auth state

---

##  3. API / Route List

| Method | Endpoint             | Description                    | Protected |
|--------|----------------------|--------------------------------|-----------|
| POST   | `/api/register`      | Register new user              | ❌        |
| POST   | `/api/login`         | Login, return JWT              | ❌        |
| GET    | `/api/profile`       | Get current user's profile     | ✅        |
| PUT    | `/api/profile`       | Update user profile            | ✅        |
| PUT    | `/api/password`      | Change user password           | ✅        |
| GET    | `/api/posts`         | Get all posts                  | ✅        |
| POST   | `/api/posts`         | Create a post                  | ✅        |
| PUT    | `/api/posts/:id`     | Edit user’s own post           | ✅        |
| DELETE | `/api/posts/:id`     | Delete user’s own post         | ✅        |

---

## 4. React Component List

- `RegisterPage`
- `LoginPage`
- `ProfilePage`
- `EditProfilePage`
- `PostFeedPage`
- `CreatePostPage`
- `PostItem` (for individual posts)
- `Navbar` (with links & logout)
- `PrivateRoute` (protect routes)
- `AuthContext` (JWT state management)
---

##  Next Steps
- Selesaikan backend route (auth, profile, posts)
- Bangun frontend layout dan routing
- Hubungkan React ke backend pakai Axios
