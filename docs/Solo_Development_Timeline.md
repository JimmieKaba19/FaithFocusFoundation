# Solo Development Timeline - FaithFocusFoundation

*For 1 developer, 10-15 hrs/week | Total: 5 weeks *

## **WHERE TO START RIGHT NOW** (Day 1 - 2 hours)

**Goal:** Get skeleton running TODAY so you see progress!

### **STEP-BY-STEP STARTING POINT:**

1. **Open Terminal in project folder**




```bash
cd faithfocusfoundation
```

2. **Install Composer dependencies** (5 mins)
   
   ```bash
   composer require phpmailer/phpmailer vlucas/phpdotenv
   ```

3. **Copy .env** (2 mins)
   
   ```bash
   cp .env.example .env
   # Open .env and add: DB_HOST=localhost, DB_NAME=faithfocus_db, etc.
   ```

4. **Start XAMPP** → Apache + MySQL running

5. **Create basic index.php** (copy this EXACT code):
   **File: `public/index.php`**
   
   ```php
   <?php
   require_once '../vendor/autoload.php';
   echo "<h1>FaithFocusFoundation - Working!</h1>";
   echo "<p>Timeline started: " . date('Y-m-d H:i') . "</p>";
   ?>
   ```

6. **Visit `http://localhost`** → See " Working!" = SUCCESS!

**Day 1 Done! Commit: `git add . && git commit -m "Initial setup working"`**

---

## **5-WEEK SOLO TIMELINE** (Build like Sanctuary)

| Week  | Phase                 | Hours | Tasks                         | Success = When You See...    |
| ----- | --------------------- | ----- | ----------------------------- | ---------------------------- |
| **1** | **SETUP + CORE**      | 10h   | Composer, DB, Routing, Layout | Home page with menu          |
| **2** | **STATIC PAGES**      | 8h    | Home, About, Programs         | 3 pages fully styled         |
| **3** | **DYNAMIC CORE**      | 12h   | Blog list + Contact form      | Blog posts show, email sends |
| **4** | **DONATIONS + ADMIN** | 10h   | Donation form + Admin login   | Admin dashboard works        |
| **5** | **TEST + DEPLOY**     | 6h    | Fix bugs, go live             | Site on real server          |

---

## **WEEK-BY-WEEK BUILD GUIDE**

*Each week builds ON the previous. Don't skip!*

### **WEEK 1: SETUP + CORE INFRASTRUCTURE** (10 hours)

**Starting Point:** Your " Working!" page
**Build Order:**

1. **Day 1:** Above steps (2h)
2. **Day 2:** Database class + connection test (3h)
3. **Day 3:** Simple router + main layout (3h)
4. **Day 4:** .htaccess + basic CSS (2h)

**Success:** Navigate `localhost/home`, `localhost/about` → styled pages load

**Files to Create:** Database.php, router.php, main.php layout

---

### **WEEK 2: STATIC PAGES** (8 hours)

**Starting Point:** Working navigation
**Build Order:**

1. **Home.php** → Mission statement + hero image (3h)
2. **About.php** → Team bios + history (3h)
3. **Programs.php** → Service list (2h)

**Success:** Mobile-friendly site with Bootstrap

---

### **WEEK 3: DYNAMIC FEATURES** (12 hours)

**Starting Point:** Static pages done
**Build Order:**

1. **BlogModel + BlogController** → List posts (4h)
2. **Blog views** → index + single post (3h)
3. **ContactController** → Form + PHPMailer (3h)
4. **Test email** → Send to yourself (2h)

**Success:** See fake blog posts, contact form emails you

---

### **WEEK 4: DONATIONS + ADMIN** (10 hours)

**Starting Point:** Blog + Contact working
**Build Order:**

1. **Donation form** → Save to DB (3h)
2. **Admin login** → Simple username/password (3h)
3. **Admin dashboard** → Add/edit blog posts (4h)

**Success:** Login as admin, add a blog post

---

### **WEEK 5: POLISH + LIVE** (6 hours)

**Starting Point:** All features work locally
**Build Order:**

1. **Security audit** → CSRF tokens (2h)
2. **Upload to hosting** → GoDaddy/HostGator (2h)
3. **Final testing** → Mobile + forms (2h)

**Success:** `https://faithfocusfoundation.org` LIVE!

---

## **DAILY WORKFLOW** (Copy this!)

```
9:00 - Open project
9:15 - Run: php -S localhost:8000 -t public/
9:20 - Work on 1 task
11:00 - Commit: git commit -m "Week1: DB connected"
11:15 - BREAK
```

## **TROUBLESHOOTING**

| Problem           | Fix                           |
| ----------------- | ----------------------------- |
| "Class not found" | `composer dump-autoload`      |
| DB error          | Check `.env` credentials      |
| Blank page        | Check `public/logs/error.log` |
| Styling broken    | Clear browser cache           |

## **PROGRESS TRACKER**

Print this! Check off daily:

Week 1: [ ] Day1 [ ] Day2 [ ] Day3 [ ] Day4
Week 2: [ ] Home [ ] About [ ] Programs
Week 3: [ ] Blog [ ] Contact
Week 4: [ ] Donations [ ] Admin
Week 5: [ ] LIVE SITE! 

---

* first updated: Oct 15, 2025*




