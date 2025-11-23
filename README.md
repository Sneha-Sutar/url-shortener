# URL Shortener
Simple Node.js + Express + Postgres URL shortener.

A full-stack URL shortener web app similar to Bit.ly.
Built for the Take-Home Assignment: TinyLink.

🚀 Features
🔗 Link Management

Create short links

Optional custom code (globally unique)

Delete links

Validate URLs before saving

Auto-generate code (6–8 characters, A–Z, a–z, 0–9)

🔁 Redirection

/:code → 302 redirect

Each visit increments click count

Updates "last clicked" timestamp

📊 Dashboard

List all links

Columns:

Short code

Target URL

Total clicks

Last clicked time

Add new link

Delete link

Search & filter

Copy short URL button

Responsive, clean UI

📈 Stats Page

Route: /code/:code

Detailed stats for a single link

❤️ Health Check

GET /healthz → returns

{ "ok": true, "version": "1.0" }

🛠️ Technologies

Backend: Node.js + Express /or Next.js (whichever you used)

Frontend: TailwindCSS / CSS

Database: Neon Postgres

Hosting: Vercel / Render / Railway

📂 Project Structure
/src
  /pages or /routes
  /components
  /lib
  /db
/public
README.md
.env.example

🔌 API Endpoints
Method	Path	Description
POST	/api/links	Create a new short link (409 if duplicate)
GET	/api/links	List all links
GET	/api/links/:code	Get stats for one link
DELETE	/api/links/:code	Delete a short link
Example Create Request
{
  "url": "https://example.com",
  "code": "custom123"
}

Example Create Response
{
  "code": "custom123",
  "url": "https://example.com",
  "shortUrl": "https://yourapp.com/custom123"
}

🧪 Automated Testing Requirements

This project respects all required conventions specified in the assignment:

Routes

Endpoint names

JSON structures

Redirect behavior

Response codes (200, 404, 409, 302)
