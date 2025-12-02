<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atik Shahriar - Portfolio</title>
    <style>
        :root{
            --bg-dark:#0d1117;
            --bg-light:#f5f5f5;
            --text-dark:#c9d1d9;
            --text-light:#0d1117;
            --accent:#007bff;
        }
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-dark);
            transition: background 0.3s, color 0.3s;
        }
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 10%;
            background-color: #161b22;
            border-bottom: 1px solid #30363d;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        header h1 {
            margin: 0;
        }
        header .title {
            font-size: 1rem;
            color: var(--accent);
        }
        nav a {
            margin-left: 15px;
            color: var(--text-dark);
            text-decoration: none;
            font-weight: bold;
        }
        nav a:hover { color: var(--accent); }
        .section {
            padding: 60px 10%;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .section.visible { opacity: 1; transform: translateY(0); }
        h2 { color: var(--accent); }
        .skills-list li, .projects-list li {
            margin: 10px 0;
        }
        .card {
            background-color: #161b22;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            border: 1px solid #30363d;
        }
        a { color: var(--accent); text-decoration: none; }
        a:hover { text-decoration: underline; }
        .profile-pic {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin-top: 20px;
        }
        .mode-toggle {
            cursor: pointer;
            background: var(--accent);
            color: #fff;
            border: none;
            padding: 8px 12px;
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <header>
        <div>
            <h1>Atik Shahriar</h1>
            <div class="title">Computer Science Student</div>
        </div>
        <nav>
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
            <button class="mode-toggle" onclick="toggleMode()">Toggle Mode</button>
        </nav>
    </header>

    <section id="about" class="section">
        <h2>About Me</h2>
        <img src="https://via.placeholder.com/120" alt="Profile Picture" class="profile-pic">
        <p>I am a computer science student passionate about web development and problem solving.</p>
    </section>

    <section id="skills" class="section">
        <h2>Skills</h2>
        <ul class="skills-list">
            <li>CSS</li>
            <li>Python</li>
            <li>Graphics Design</li>
            <li>Communication Skills</li>
        </ul>
    </section>

    <section id="projects" class="section">
        <h2>Projects</h2>
        <ul class="projects-list">
            <li class="card">2D Game Development</li>
        </ul>
    </section>

    <section id="contact" class="section">
        <h2>Contact</h2>
        <p>Email: <a href="mailto:shahriaratik577@gmail.com">shahriaratik577@gmail.com</a></p>
        <p>Phone: <a href="tel:+918944082010">+91 89440 82010</a></p>
        <p>Facebook: <a href="https://www.facebook.com/AtikShahriarRajin">Atik Shahriar Rajin</a></p>
        <p>Instagram: <a href="https://instagram.com/atiksr_1342">@atiksr_1342</a></p>
        <p>LinkedIn: <a href="https://www.linkedin.com/in/24BCS10267">24BCS10267</a></p>
    </section>

    <script>
        function toggleMode() {
            const body = document.body;
            if (body.style.backgroundColor === 'var(--bg-light)') {
                body.style.backgroundColor = 'var(--bg-dark)';
                body.style.color = 'var(--text-dark)';
            } else {
                body.style.backgroundColor = 'var(--bg-light)';
                body.style.color = 'var(--text-light)';
            }
        }

        // Scroll animations
        const sections = document.querySelectorAll('.section');
        window.addEventListener('scroll', () => {
            const triggerBottom = window.innerHeight / 5 * 4;
            sections.forEach(section => {
                const sectionTop = section.getBoundingClientRect().top;
                if(sectionTop < triggerBottom){
                    section.classList.add('visible');
                }
            });
        });
    </script>
</body>
</html>
