<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bhagyashree N | Portfolio</title>
  <style>
    :root {
      --primary-color: #6c63ff;
      --bg-color: #f9f9f9;
      --text-color: #333;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background-color: var(--bg-color);
      color: var(--text-color);
    }

    header {
      background: linear-gradient(to right, #6c63ff, #3b3b98);
      color: white;
      padding: 2rem 1rem;
      text-align: center;
    }

    nav ul {
      display: flex;
      justify-content: center;
      gap: 2rem;
      padding: 0;
      list-style: none;
      margin: 1rem 0 0;
    }

    nav a {
      color: white;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s ease;
    }

    nav a:hover {
      color: #ffd369;
    }

    section {
      max-width: 1000px;
      margin: 2rem auto;
      background: white;
      padding: 2rem;
      border-radius: 1rem;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.05);
    }

    h1, h2, h3 {
      color: var(--primary-color);
    }

    .profile {
      text-align: center;
    }

    .profile img {
      width: 160px;
      height: 160px;
      border-radius: 50%;
      object-fit: cover;
      margin-bottom: 1rem;
    }

    ul {
      padding-left: 1.2rem;
    }

    .resume-link a {
      display: inline-block;
      margin-top: 1rem;
      background-color: #6c63ff;
      color: white;
      padding: 0.8rem 1.5rem;
      text-decoration: none;
      border-radius: 30px;
      font-weight: bold;
    }

    form input, form textarea {
      width: 100%;
      padding: 0.8rem;
      margin-bottom: 1rem;
      border-radius: 8px;
      border: 1px solid #ccc;
    }

    form button {
      background-color: var(--primary-color);
      color: white;
      padding: 0.8rem 2rem;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      font-weight: bold;
    }

    footer {
      text-align: center;
      background-color: #3b3b98;
      color: white;
      padding: 1rem;
      margin-top: 3rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Bhagyashree N</h1>
    <p>Java Full Stack Developer</p>
    <nav>
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section id="about" class="profile">
    <h2>About Me</h2>
    <img src="bhagya img.jpeg" alt="Bhagyashree N">
    <p>I am a Java Full Stack Developer with strong academic grounding and hands-on project experience. Skilled in building responsive web applications using Java, Spring Boot, HTML, CSS, and JavaScript. Passionate about solving real-world problems with elegant and efficient code.</p>
    <div class="resume-link">
      <a href="https://drive.google.com/file/d/1GRQ7JLgIZ4clJTCOw4jpYq5UpMmZhNAH/view?usp=sharing" target="_blank">Download My Resume</a>
    </div>
  </section>

  <section id="skills">
    <h2>Skills</h2>
    <ul>
      <li><strong>Programming:</strong> Java, JavaScript</li>
      <li><strong>Frameworks:</strong> Spring Boot, Hibernate</li>
      <li><strong>Frontend:</strong> HTML, CSS, JavaScript</li>
      <li><strong>Database:</strong> MySQL</li>
      <li><strong>Tools:</strong> Git, GitHub, Eclipse, VS Code, AWS, Maven, Docker, Jenkins, Kubernetes, Terraform</li>
    </ul>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <h3>Sharnbasva University Online Evaluation System</h3>
    <p><strong>Objective:</strong> A web-based application to simplify and digitalize the evaluation process for PhD students, aiming to reduce manual work, save time, and bring transparency.</p>
    <p><strong>Key Features:</strong></p>
    <ul>
      <li>User Management for Faculty and PhD students</li>
      <li>Thesis Upload and Secure Storage</li>
      <li>Three-level Evaluation (Mentor, HOD, Dean)</li>
      <li>OTP-based Result Access</li>
    </ul>
    <p><strong>Tech Stack:</strong> HTML, CSS, JavaScript (Frontend); Java (Backend)</p>
    <p><strong>My Role:</strong> UI Design, Logic Implementation, Java Backend Integration</p>
  </section>

  <section id="contact">
    <h2>Contact</h2>
    <form id="contactForm">
      <input type="text" id="name" name="name" placeholder="Your Name" required>
      <input type="email" id="email" name="email" placeholder="Your Email" required>
      <textarea id="message" name="message" rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    <p id="responseMsg"></p>
    <p>Email: <a href="mailto:your.email@example.com">your.email@example.com</a></p>
    <p>Phone: 9901118482</p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/bhagyashreebijap/" target="_blank">Bhagyashree on LinkedIn</a></p>
    <p>GitHub: <a href="https://github.com/BhagyashreeNBijap" target="_blank">Bhagyashree on GitHub</a></p>
  </section>

  <footer>
    <p>&copy; 2025 Bhagyashree N. All rights reserved.</p>
  </footer>

  <script>
    document.getElementById("contactForm").addEventListener("submit", async function (e) {
      e.preventDefault();
      const formData = {
        name: document.getElementById("name").value,
        email: document.getElementById("email").value,
        message: document.getElementById("message").value,
      };
      try {
        const res = await fetch("http://localhost:8080/contact", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify(formData)
        });
        const result = await res.text();
        document.getElementById("responseMsg").innerText = result;
        document.getElementById("contactForm").reset();
      } catch (err) {
        document.getElementById("responseMsg").innerText = "Failed to send message. Try again later.";
      }
    });
  </script>
</body>
</html>
