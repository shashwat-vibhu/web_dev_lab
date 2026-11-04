# Web Development Lab Practicals

**Course:** Programming for Web Development - I  
**Course Code:** BTBC123

This repository contains the solutions for all 13 Web Development lab practicals. Each practical is kept in this README so everything stays together in one place.

---

## Module 1: Terminal, Git & GitHub

### P1: Project folder and terminal navigation

**Aim:** Create a project folder and practise moving between folders using Terminal.

**Commands:**

~~~bash
cd ~/Desktop
mkdir WebProject
cd WebProject
pwd
mkdir css images js
ls
cd css
cd ..
~~~

**What these commands do:**
- `cd` changes the current directory.
- `mkdir` creates a new folder.
- `pwd` shows the current folder path.
- `ls` lists the files and folders.
- `cd ..` moves one level back.

**Expected structure:**

~~~text
WebProject/
├── css/
├── images/
└── js/
~~~

### P2: Portfolio repo with an initial commit

**Aim:** Create a basic portfolio project, initialise Git and make the first commit.

Create a file named `index.html`:

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
</head>
<body>
    <header>
        <h1>My Portfolio</h1>
        <p>Welcome to my personal website.</p>
    </header>

    <main>
        <section>
            <h2>About Me</h2>
            <p>I am a student learning web development.</p>
        </section>
    </main>

    <footer>
        <p>Copyright 2026</p>
    </footer>
</body>
</html>
~~~

**Git commands:**

~~~bash
git init
git add .
git commit -m "Initial commit"
~~~

To connect the local project to a GitHub repository, add its remote URL and push the commit:

~~~bash
git remote add origin https://github.com/your-username/your-repository.git
git branch -M main
git push -u origin main
~~~

Replace the example URL with the URL of your own repository.

### P3: Feature-branch Git workflow

**Aim:** Practise creating a branch, making a change and merging it into the main branch.

~~~bash
git switch -c feature/about-section
~~~

Make a small change to the portfolio, then run:

~~~bash
git status
git add .
git commit -m "Add about section"
git switch main
git merge feature/about-section
git push origin main
~~~

**Explanation:**
- `git switch -c` creates and moves to a new branch.
- `git status` shows changed files.
- `git add .` stages the changes.
- `git commit` saves the staged changes.
- `git merge` combines the feature branch with the current branch.
- `git push` uploads local commits to GitHub.

### P4: GitHub README and version tags

**Aim:** Create a README file and mark a version of the project using a Git tag.

Example README content:

~~~markdown
# My Portfolio

This is my personal portfolio website.

## Sections
- About Me
- Skills
- Projects
- Contact

## Technologies
- HTML
- CSS
- JavaScript
~~~

After saving it as `README.md`, run:

~~~bash
git add README.md
git commit -m "Add project README"
git tag -a v1.0 -m "First version"
git push origin main
git push origin v1.0
~~~

A tag such as `v1.0` marks a particular version of the project.

---

## Module 2: HTML & CSS Foundations

### P5: Semantic bio page

**Aim:** Create a personal biography page using semantic HTML elements.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Bio</title>
</head>
<body>
    <header>
        <h1>Shaswat Vibhu</h1>
        <p>B.Tech CSE (AI & ML) Student</p>
    </header>

    <main>
        <section>
            <h2>Introduction</h2>
            <p>I am a student interested in programming and web development.</p>
        </section>

        <section>
            <h2>Education</h2>
            <p>B.Tech CSE (AI & ML), Bosscoder School of Technology.</p>
        </section>

        <section>
            <h2>Skills</h2>
            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>Java</li>
            </ul>
        </section>

        <article>
            <h2>Hobbies</h2>
            <p>I enjoy learning new technologies and solving problems.</p>
        </article>

        <aside>
            <h2>Interests</h2>
            <p>Web development and computer science.</p>
        </aside>
    </main>

    <footer>
        <p>Contact: shaswat@example.com</p>
    </footer>
</body>
</html>
~~~

**Semantic elements used:** `header` contains introductory content, `main` holds the main page content, `section` groups related information, `article` holds a self-contained part, `aside` contains additional information and `footer` contains contact or closing details.

### P6: Full portfolio page structure in semantic HTML

**Aim:** Build a portfolio structure with navigation, About, Skills, Projects, Education and footer sections.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
</head>
<body>
    <header>
        <h1>Shaswat Vibhu</h1>
        <nav>
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#education">Education</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main>
        <section id="about">
            <h2>About Me</h2>
            <p>I am a B.Tech student interested in computer science and technology.</p>
        </section>

        <section id="skills">
            <h2>Skills</h2>
            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>Java</li>
            </ul>
        </section>

        <section id="projects">
            <h2>Projects</h2>
            <article>
                <h3>Personal Portfolio</h3>
                <p>A simple website made using HTML and CSS.</p>
            </article>
        </section>

        <section id="education">
            <h2>Education</h2>
            <p>B.Tech CSE (AI & ML) - Bosscoder School of Technology</p>
        </section>
    </main>

    <footer id="contact">
        <h2>Contact</h2>
        <p>Email: shaswat@example.com</p>
    </footer>
</body>
</html>
~~~

### P7: Design tokens and typography system in CSS

**Aim:** Use reusable CSS variables for colours, fonts, font sizes and spacing.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Design System</title>
    <style>
        :root {
            --primary: #164a7a;
            --background: #f4f7fb;
            --text: #222222;
            --card: #ffffff;
            --font-main: Arial, sans-serif;
            --space-small: 10px;
            --space-medium: 20px;
            --space-large: 30px;
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            padding: var(--space-large);
            background-color: var(--background);
            color: var(--text);
            font-family: var(--font-main);
            line-height: 1.6;
        }

        h1, h2 {
            color: var(--primary);
        }

        p {
            font-size: 16px;
        }

        .card {
            background-color: var(--card);
            padding: var(--space-medium);
            margin-bottom: var(--space-medium);
            border-radius: 10px;
        }

        button {
            background-color: var(--primary);
            color: white;
            padding: var(--space-small) var(--space-medium);
            border: none;
            border-radius: 6px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>My Design System</h1>
    <div class="card">
        <h2>Welcome</h2>
        <p>This card uses reusable design values from CSS variables.</p>
        <button>Read More</button>
    </div>
</body>
</html>
~~~

**Note:** Variables declared inside `:root` can be reused throughout the stylesheet with `var(--variable-name)`. This makes common design changes easier.

### P8: Sticky navbar and card overlay using CSS positioning

**Aim:** Keep the navigation bar visible while scrolling and place an overlay on a card.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sticky Navbar and Overlay</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        nav {
            position: sticky;
            top: 0;
            background-color: #164a7a;
            padding: 15px;
            color: white;
            z-index: 10;
        }

        .card {
            position: relative;
            width: 300px;
            margin: 40px auto;
        }

        .card img {
            width: 100%;
            display: block;
            border-radius: 10px;
        }

        .overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 15px;
            box-sizing: border-box;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
        }

        .content {
            height: 900px;
            padding: 20px;
        }
    </style>
</head>
<body>
    <nav>My Website</nav>

    <div class="card">
        <img src="https://via.placeholder.com/300x200" alt="Sample card">
        <div class="overlay">
            <h3>Project Card</h3>
            <p>Text placed over the image.</p>
        </div>
    </div>

    <div class="content">
        <h2>Scroll the page</h2>
        <p>The navigation bar stays at the top.</p>
    </div>
</body>
</html>
~~~

**Important properties:** `position: sticky` keeps the navbar in view after it reaches the top. The card uses `position: relative`, which makes it the positioning reference for the absolutely positioned overlay.

### P9: Responsive navbar and card grid using Flexbox

**Aim:** Use Flexbox to arrange navigation links and cards, allowing the layout to adjust to smaller screens.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Flexbox Layout</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            padding: 20px;
            background-color: #164a7a;
        }

        nav a {
            color: white;
            text-decoration: none;
        }

        .cards {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            padding: 20px;
        }

        .card {
            flex: 1 1 220px;
            padding: 25px;
            background-color: #eeeeee;
            border-radius: 10px;
        }

        @media (max-width: 600px) {
            nav {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    </style>
</head>
<body>
    <nav>
        <strong><a href="#">My Portfolio</a></strong>
        <div>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <main class="cards">
        <div class="card"><h2>HTML</h2><p>Page structure.</p></div>
        <div class="card"><h2>CSS</h2><p>Page styling.</p></div>
        <div class="card"><h2>JavaScript</h2><p>Page interaction.</p></div>
    </main>
</body>
</html>
~~~

**Flexbox properties used:** `display: flex` enables Flexbox, `justify-content` distributes items, `align-items` aligns them on the cross axis, `flex-wrap` allows items to move to another line and `gap` adds space between items.

---

## Module 3: CSS Layout Systems

### P10: Portfolio header and footer with advanced Flexbox

**Aim:** Arrange the logo, navigation links and footer information using Flexbox.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio Flexbox Layout</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            font-family: Arial, sans-serif;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
            padding: 20px;
            background-color: #164a7a;
            color: white;
        }

        nav {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }

        nav a {
            color: white;
            text-decoration: none;
        }

        main {
            flex: 1;
            padding: 30px;
        }

        footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
            padding: 20px;
            background-color: #164a7a;
            color: white;
        }

        @media (max-width: 600px) {
            header, footer {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>My Portfolio</h1>
        <nav>
            <a href="#about">About</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main>
        <h2>Welcome</h2>
        <p>This is my portfolio website.</p>
    </main>

    <footer>
        <p>© 2026 My Portfolio</p>
        <p>Email: shaswat@example.com</p>
        <p>Social: GitHub | LinkedIn</p>
    </footer>
</body>
</html>
~~~

**Why use `flex: 1` on main?** It allows the main section to take up available vertical space, helping keep the footer near the bottom when the page has little content.

### P11: Newspaper-style three-column layout with CSS Grid

**Aim:** Create a newspaper page with a main headline, articles and side news using three Grid columns.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily News</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            padding: 20px;
            font-family: Georgia, serif;
            background-color: #f5f5f5;
        }

        header {
            text-align: center;
            border-bottom: 3px solid #222;
            margin-bottom: 20px;
        }

        .news-grid {
            display: grid;
            grid-template-columns: 1fr 2fr 1fr;
            gap: 20px;
        }

        .news-grid article {
            padding: 15px;
            background-color: #eeeeee;
        }

        .main-news {
            background-color: #dff6ff;
        }

        .news-grid img {
            width: 100%;
            height: auto;
        }

        @media (max-width: 700px) {
            .news-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>The Daily News</h1>
        <p>News from around the world</p>
    </header>

    <main class="news-grid">
        <article>
            <h2>City News</h2>
            <p>Updates and events from the city.</p>
        </article>

        <article class="main-news">
            <h2>Main Headline: Technology Is Changing Education</h2>
            <img src="https://via.placeholder.com/500x220" alt="Technology and education">
            <p>Digital tools are changing how students learn and access information.</p>
        </article>

        <article>
            <h2>Sports News</h2>
            <p>Latest updates from the world of sports.</p>
        </article>
    </main>
</body>
</html>
~~~

**Grid explanation:** `grid-template-columns: 1fr 2fr 1fr` creates three columns. The middle column gets twice the available space of either side column. The media query changes the layout to one column on smaller screens.

### P12: Portfolio projects grid with advanced CSS Grid

**Aim:** Create project cards using Grid with different column sizes, gaps and item placement.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Projects</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            padding: 25px;
            font-family: Arial, sans-serif;
            background-color: #f4f7fb;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            grid-auto-rows: minmax(150px, auto);
            gap: 20px;
        }

        .project {
            padding: 25px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        .featured {
            grid-column: span 2;
        }

        @media (max-width: 600px) {
            .featured {
                grid-column: span 1;
            }
        }
    </style>
</head>
<body>
    <h1>My Projects</h1>

    <main class="projects">
        <article class="project featured">
            <h2>Portfolio Website</h2>
            <p>A personal website built with HTML and CSS.</p>
        </article>

        <article class="project">
            <h2>Calculator</h2>
            <p>A simple calculator project.</p>
        </article>

        <article class="project">
            <h2>Student Page</h2>
            <p>A page showing student information.</p>
        </article>

        <article class="project">
            <h2>News Layout</h2>
            <p>A newspaper-style Grid layout.</p>
        </article>
    </main>
</body>
</html>
~~~

**Grid properties used:**
- `repeat(auto-fit, minmax(220px, 1fr))` creates as many columns as can fit, with each column at least 220px wide.
- `gap` sets the space between cards.
- `grid-column: span 2` makes the featured card cover two columns.
- The media query makes the featured card use one column on narrow screens.

### P13: Choosing between Flexbox and Grid for a shared layout

**Aim:** Use Flexbox for a one-dimensional navigation bar, Grid for a two-dimensional content area and Flexbox for a row of cards.

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox and Grid</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            padding: 20px;
            background-color: #164a7a;
        }

        nav a {
            color: white;
            text-decoration: none;
        }

        .cards {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            padding: 20px;
        }

        .card {
            flex: 1 1 180px;
            padding: 20px;
            background-color: #eeeeee;
        }

        .content-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
            padding: 20px;
        }

        .content-grid article,
        .content-grid aside {
            padding: 20px;
            background-color: #dff6ff;
        }

        @media (max-width: 600px) {
            .content-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav>
        <strong><a href="#">My Website</a></strong>
        <div>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <section class="cards">
        <div class="card"><h2>HTML</h2><p>Structure</p></div>
        <div class="card"><h2>CSS</h2><p>Styling</p></div>
        <div class="card"><h2>JavaScript</h2><p>Interaction</p></div>
    </section>

    <main class="content-grid">
        <article>
            <h2>Main Content</h2>
            <p>This is the main content area of the page.</p>
        </article>

        <aside>
            <h2>Sidebar</h2>
            <p>Extra information goes here.</p>
        </aside>
    </main>
</body>
</html>
~~~

**Why these layout choices?**
- **Flexbox for the navbar:** its items are arranged in one direction.
- **Flexbox for the cards:** cards can wrap onto another line when space is limited.
- **Grid for the content and sidebar:** it controls rows and columns together, making it suitable for a two-dimensional layout.

---

## Quick revision

| Practical | Main concept |
|---|---|
| P1 | Terminal commands and folders |
| P2 | Git initialisation and first commit |
| P3 | Branching and merging |
| P4 | README and Git tags |
| P5 | Semantic HTML |
| P6 | Portfolio page structure |
| P7 | CSS variables and typography |
| P8 | Sticky and absolute positioning |
| P9 | Responsive Flexbox |
| P10 | Advanced Flexbox |
| P11 | Three-column CSS Grid |
| P12 | Advanced CSS Grid |
| P13 | Choosing Flexbox or Grid |

**Note:** Replace sample email addresses, text and placeholder images with your own details before submitting the practicals.
