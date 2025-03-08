

# 🌍 Family Travel Tracker  

### 🏡 Keep track of where your family has traveled!  

## 📌 About the Project  
**Family Travel Tracker** is a simple yet powerful Node.js and Express application that allows users to log the countries they have visited. It stores users and their visited destinations in a PostgreSQL database and provides an interactive interface to view and update travel records.  
## Preview  
![Family Travel Tracker Preview](p1.png)

![Family Travel Tracker Preview](p2.png)

## ⚡ Features  
✅ Add and manage family members 🏠  
✅ Assign a unique color to each user 🎨  
✅ Log visited countries 🌎  
✅ View travel history dynamically 📊  
✅ PostgreSQL-powered database integration 💾  

## 🏗️ Tech Stack  
- **Backend:** Node.js, Express.js  
- **Database:** PostgreSQL  
- **Frontend:** EJS, HTML, CSS  
- **Deployment:** Local development (Can be hosted on platforms like Heroku or Vercel)  

## 📂 Database Schema  
### Users Table (`users`)  
| Column  | Type          | Constraints           |  
|---------|--------------|-----------------------|  
| `id`    | SERIAL       | PRIMARY KEY           |  
| `name`  | VARCHAR(15) | UNIQUE, NOT NULL      |  
| `color` | VARCHAR(15) |                        |  

### Visited Countries Table (`visited_countries`)  
| Column         | Type    | Constraints                     |  
|---------------|--------|---------------------------------|  
| `id`          | SERIAL | PRIMARY KEY                     |  
| `country_code`| CHAR(2)| NOT NULL                        |  
| `user_id`     | INTEGER| REFERENCES `users(id)` (FK)    |  

## 🛠️ Installation & Setup  
1️⃣ Clone the repository:  
```sh
git clone https://github.com/saadhtiwana/family-travel-tracker.git
cd family-travel-tracker
```  
2️⃣ Install dependencies:  
```sh
npm install
```  
3️⃣ Set up the PostgreSQL database:  
- Create a database named `world`  
- Run the following SQL commands to set up tables:  
```sql
DROP TABLE IF EXISTS visited_countries, users;

CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(15) UNIQUE NOT NULL,
  color VARCHAR(15)
);

CREATE TABLE visited_countries (
  id SERIAL PRIMARY KEY,
  country_code CHAR(2) NOT NULL,
  user_id INTEGER REFERENCES users(id)
);

INSERT INTO users (name, color)
VALUES ('Saad', 'green'), ('Fahad', 'blue');

INSERT INTO visited_countries (country_code, user_id)
VALUES ('FR', 1), ('GB', 1), ('CA', 2), ('FR', 2);
```  

4️⃣ Start the server:  
```sh
npm start
```  
Server runs on **http://localhost:3000** 🚀  

## 📧 Contact  
👨‍💻 **Saad Tiwana**  
📩 Email: [saadhayat799@gmail.com](mailto:saadhayat799@gmail.com)  
🔗 GitHub: [saadhtiwana](https://github.com/saadhtiwana)  
