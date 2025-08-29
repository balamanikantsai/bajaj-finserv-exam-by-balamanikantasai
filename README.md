# bajaj-finserv-exam-by-balamanikantasai

Got it ✅ — you just want a **REST API design section** (not the full README).
Here’s a clean **REST API Design** you can drop into your README:

---

## 🌐 REST API Design

| Method   | Endpoint               | Description                                                  |
| -------- | ---------------------- | ------------------------------------------------------------ |
| **POST** | `/api/submit`          | Trigger the workflow (generate webhook → pick SQL → submit). |
| **GET**  | `/api/status/{regNo}`  | Get the last submission status for a candidate.              |
| **GET**  | `/api/sql/{problemId}` | Retrieve the SQL query for a problem (`Q1` or `Q2`).         |

---

### 1. `POST /api/submit`

**Request Body**

```json
{
  "name": "Your Name",
  "regNo": "REG12347",
  "email": "you@example.com"
}
```

**Response Example**

```json
{
  "webhook": "https://bfhldevapigw.healthrx.co.in/hiring/submit/data/JAVA/abc123",
  "chosenProblem": "Q1",
  "finalQuery": "SELECT ...",
  "status": "200 OK",
  "submissionResponse": "{...raw response from API...}"
}
```

---

### 2. `GET /api/status/{regNo}`

**Response Example**

```json
{
  "regNo": "REG12347",
  "chosenProblem": "Q1",
  "submittedAt": "2025-08-29T11:20:34Z",
  "status": "200 OK"
}
```

---

### 3. `GET /api/sql/{problemId}`

**Example:**
`GET /api/sql/Q1`

**Response Example**

```json
{
  "problemId": "Q1",
  "sql": "SELECT ... LIMIT 1;"
}
```

---

👉 This API design is simple, RESTful, and testable via Postman or cURL.

Do you also want me to include an **API sequence diagram** (showing how your app → BFHL APIs → webhook works), or only keep these REST endpoints?
