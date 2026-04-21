# LibriTrack - Personal Reading Goal & Insight Engine

**Live Application:** (https://www.google.com/search?q=https://libritracker.vercel.app)

### The Problem

Avid readers often struggle to turn "reading" into "retaining." While people set ambitious annual goals, they frequently lose track of their progress and forget the impactful quotes that made a book worth reading in the first place. **LibriTrack** provides a centralized space to quantify reading habits and archive intellectual highlights.

### System Architecture

```text
Browser (React + Vite)
       |
       |  HTTPS + JWT Auth Header
       v
Node.js / Express API
       |
       |-----------------------|
       v                       v
MongoDB (Atlas)         Auth Middleware
(Goals/Books/Quotes)     (Bcrypt / JWT)
```

### Technical Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | React 18 | Single Page Application & State Management |
| **Backend** | Node.js + Express | RESTful API Design |
| **Database** | MongoDB | Document storage for nested quotes & book data |
| **Auth** | JWT & Bcrypt | Secure user sessions and password hashing |

-----

## Technical Reflection & Future Growth

### What I Would Do Differently

  * **Secure Token Storage:** Currently, JWTs are stored in `localStorage`, which is vulnerable to XSS attacks. In a v2 release, I would refactor the authentication flow to use **HttpOnly Cookies** with a Refresh Token pattern to significantly harden the application's security.
  * **Search Optimization:** The current book search performs basic MongoDB queries. As the dataset grows, this will become slow. For v2, I would implement **Atlas Search (Lucene)** or add **Compound Indexes** on the `title` and `author` fields to ensure sub-100ms response times for users.

-----

