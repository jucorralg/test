
---

## Setup and Deployment

### 1. Backend (Render)

1. Create a **Web Service** in Render: `NovaPay`
2. Connect GitHub repository `MockPayment`
3. Environment Variables:
   - `REDIS_URL` → Redis connection string (from Render Key-Value service)
   - `FRONTEND_URL` → `https://jucorralg.github.io/MockPayment/backend/frontend`
4. Build Command: `npm install`
5. Start Command: `node server.js`
6. Expose port: default `3000`

---

### 2. Frontend (GitHub Pages)

1. Push `backend/frontend/index.html` to your GitHub repository
2. Enable GitHub Pages from the repository settings
3. URL will be:  
   `https://jucorralg.github.io/MockPayment/backend/frontend/index.html`

---

### 3. Redis (Render Key-Value)

1. Create a Key-Value service `Novapay-redis`
2. Use URL: `redis://red-d6bcjbggjchc73ahno00:6379`
3. Assign this URL to the `REDIS_URL` environment variable in the Render web service

---

## APIs

### 1. Create Payment Session

**Endpoint:** `POST /api/create-session`  
**Request Body:**

```json
{
  "amount": 100.50,
  "customerEmail": "customer@example.com",
  "agentId": "agent-123"
}
```
