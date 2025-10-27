**CORS (Cross-Origin Resource Sharing)** is a **security mechanism** built into web browsers that controls how a webpage can make requests to a different domain (or *origin*) than the one that served it.  

---

### 🔹 The Problem It Solves
By default, browsers enforce the **Same-Origin Policy (SOP)** — meaning that scripts running on `https://example.com` can’t directly make AJAX or `fetch()` requests to `https://api.anotherdomain.com`.  
This prevents malicious scripts from reading sensitive data from another site (like your banking session).

---

### 🔹 How CORS Works
CORS is a **server-side opt-in** mechanism that relaxes this restriction **safely**.

When a browser makes a cross-origin request:
1. The **browser** automatically adds an `Origin` header to the request — e.g.  
   ```
   Origin: https://example.com
   ```
2. The **server** responds with one or more `Access-Control-*` headers.  
   The most important is:  
   ```
   Access-Control-Allow-Origin: https://example.com
   ```
   or  
   ```
   Access-Control-Allow-Origin: *
   ```
3. The **browser** checks if the server’s response allows the origin making the request.
   - If yes → the response is passed to JavaScript.
   - If not → the browser blocks the response and throws a CORS error (even though the request technically reached the server).

---

### 🔹 Types of CORS Requests
1. **Simple requests** (GET/POST with standard headers like `Content-Type: application/x-www-form-urlencoded`)  
   → Sent directly, CORS headers checked in response.
2. **Preflighted requests** (anything else: custom headers, `PUT`, `DELETE`, JSON, etc.)  
   → Browser first sends an **OPTIONS** request to check if the actual request is allowed.  
     The server must respond with:  
     ```
     Access-Control-Allow-Methods: GET, POST, OPTIONS
     Access-Control-Allow-Headers: Content-Type
     Access-Control-Allow-Origin: https://example.com
     ```
     Only if the preflight passes does the browser send the real request.

---

### 🔹 In Practice
If you see:
```
Access to fetch at 'https://api.foo.com/data' from origin 'https://bar.com' has been blocked by CORS policy
```
→ It means your browser received a response, but the **server didn’t include the right CORS headers** to allow `https://bar.com` to access it.

---

### 🔹 Key Point
CORS is **enforced by browsers**, not by servers.  
- Server-to-server requests (like in Node.js or Apex callouts) aren’t subject to CORS.
- CORS only affects **frontend code running in browsers**.

---