<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Avhi | Video Editor Portfolio</title>
    <style>
        :root {
            --bg-color: #ffffff;
            --light-purple: #f5edff; 
            --accent-purple: #c084fc; 
            --text-dark: #333333;
            --text-light: #666666;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--bg-color);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animations Setup */
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in-down { animation: fadeInDown 1s ease-out forwards; }
        .fade-in-up { 
            animation: fadeInUp 1s ease-out forwards; 
            opacity: 0; 
        }

        .delay-1 { animation-delay: 0.2s; }
        .delay-2 { animation-delay: 0.4s; }
        .delay-3 { animation-delay: 0.6s; }
        .delay-4 { animation-delay: 0.8s; }

        header {
            background-color: var(--bg-color);
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(192, 132, 252, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5em;
            font-weight: 800;
            color: var(--accent-purple);
            text-decoration: none;
            transition: transform 0.3s ease;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .hero {
            text-align: center;
            padding: 80px 20px;
            background: linear-gradient(135deg, #ffffff 0%, var(--light-purple) 100%);
            border-radius: 20px;
            margin-bottom: 60px;
            box-shadow: 0 10px 30px rgba(192, 132, 252, 0.05);
        }

        .hero h1 {
            font-size: 3.5em;
            margin-bottom: 10px;
            color: var(--text-dark);
        }

        .hero h1 span {
            color: var(--accent-purple);
        }

        .hero p {
            font-size: 1.2em;
            color: var(--text-light);
            max-width: 600px;
            margin: 0 auto 20px auto;
        }

        .experience-badge {
            display: inline-block;
            background-color: white;
            color: var(--accent-purple);
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 0.9em;
            border: 1px solid var(--accent-purple);
            margin-bottom: 30px;
            transition: all 0.3s ease;
        }

        .experience-badge:hover {
            background-color: var(--accent-purple);
            color: white;
        }

        .section-title {
            text-align: center;
            font-size: 2.2em;
            margin-bottom: 40px;
            color: var(--text-dark);
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-bottom: 70px;
        }

        .skill-card {
            background-color: white;
            padding: 30px 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(192, 132, 252, 0.1);
            border-bottom: 3px solid var(--accent-purple);
            transition: all 0.4s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 8px 25px rgba(192, 132, 252, 0.2);
        }

        .skill-card h3 {
            margin: 0;
            color: var(--accent-purple);
            font-size: 1.3em;
            margin-bottom: 10px;
        }

        /* Work Section */
        .work-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Adjusted column width */
            gap: 25px;
            margin-bottom: 70px;
            justify-content: center;
        }

        .video-card {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(192, 132, 252, 0.15);
            transition: transform 0.4s ease;
            text-align: center;
            padding-bottom: 15px;
            max-width: 230px; /* Limits max size to make boxes smaller */
            width: 100%;
            margin: 0 auto; /* Centers the box inside its grid column */
        }

        .video-card:hover {
            transform: scale(1.03);
            box-shadow: 0 10px 30px rgba(192, 132, 252, 0.3);
        }

        .video-card iframe {
            width: 100%;
            aspect-ratio: 9/16; 
            border: none;
        }

        .video-card h3 {
            color: var(--text-dark);
            margin: 15px 0 5px 0;
            font-size: 1.05em;
        }

        /* Contact Section */
        .contact-section {
            background-color: var(--light-purple);
            padding: 60px 20px;
            text-align: center;
            border-radius: 20px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 15px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1em;
            transition: all 0.3s ease;
        }

        .btn-whatsapp {
            background-color: #25D366;
            color: white;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.3);
        }

        .btn-whatsapp:hover {
            background-color: #128C7E;
            transform: translateY(-5px);
            box-shadow: 0 6px 20px rgba(37, 211, 102, 0.4);
        }

        .btn-email {
            background-color: var(--accent-purple);
            color: white;
            box-shadow: 0 4px 15px rgba(192, 132, 252, 0.3);
        }

        .btn-email:hover {
            background-color: #a855f7;
            transform: translateY(-5px);
            box-shadow: 0 6px 20px rgba(192, 132, 252, 0.4);
        }

        footer {
            text-align: center;
            padding: 30px;
            color: var(--text-light);
            font-size: 0.9em;
        }
    </style>
</head>
<body>

    <header class="fade-in-down">
        <a href="#" class="logo">@editoravii</a>
    </header>

    <div class="container">
        <section class="hero fade-in-up delay-1">
            <div class="experience-badge">1+ Year Experience</div>
            <h1>Hi, I'm <span>Avhi</span></h1>
            <p>A passionate freelance video editor specializing in aesthetic mobile edits, bringing your vision to life through smooth transitions and clean visuals.</p>
        </section>

        <h2 class="section-title fade-in-up delay-2">What I Can Do</h2>
        <div class="skills-grid">
            <div class="skill-card fade-in-up delay-1">
                <h3>Motion Graphics</h3>
                <p>Smooth, dynamic text and graphic animations to elevate your content.</p>
            </div>
            <div class="skill-card fade-in-up delay-2">
                <h3>Clean Edits</h3>
                <p>Crisp, professional cuts focusing on storytelling and flow.</p>
            </div>
            <div class="skill-card fade-in-up delay-3">
                <h3>AMV Edits</h3>
                <p>High-energy Anime Music Videos with perfect beat sync and effects.</p>
            </div>
            <div class="skill-card fade-in-up delay-4">
                <h3>Mobile Editing</h3>
                <p>Expertise in top mobile software to deliver quick and aesthetic results.</p>
            </div>
        </div>

        <h2 class="section-title fade-in-up delay-1">My Work</h2>
        <div class="work-grid">
            <div class="video-card fade-in-up delay-1">
                <iframe src="https://www.youtube.com/embed/hoBXQ3rppWA" title="AMV Edit" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3>AMV Edit</h3>
            </div>
            <div class="video-card fade-in-up delay-2">
                <iframe src="https://www.youtube.com/embed/hQ_2VHrkCZo" title="Motion Graphics Edit" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3>Motion Graphics</h3>
            </div>
            <div class="video-card fade-in-up delay-3">
                <iframe src="https://www.youtube.com/embed/VwzChyF8h5Q" title="Clean Edit" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3>Clean Edit</h3>
            </div>
            <div class="video-card fade-in-up delay-4">
                <iframe src="https://www.youtube.com/embed/-dw9nM_n2y4" title="Caption Clean Edit" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                <h3>Caption Clean Edit</h3>
            </div>
        </div>

        <section class="contact-section fade-in-up delay-2">
            <h2 class="section-title" style="margin-bottom: 10px;">Let's Work Together</h2>
            <p>Ready to upgrade your videos? Drop me a message and let's discuss your next project.</p>
            
            <div class="contact-links">
                <a href="https://wa.me/917898087582" target="_blank" class="btn btn-whatsapp">📱 Chat on WhatsApp</a>
                <a href="mailto:avhifreelancer@gmail.com" class="btn btn-email">✉️ Send an Email</a>
            </div>
        </section>
    </div>

    <footer class="fade-in-up delay-3">
        &copy; 2026 Avhi (@editoravii). All rights reserved.
    </footer>

</body>
</html>
