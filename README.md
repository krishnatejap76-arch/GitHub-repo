<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Web Architect Workshop</title>
    <style>
        :root {
            --lamp-body: #222;
            --thread-glow: #ffffff;
            --accent-purple: #a29bfe;
            --bg-dark: #000000;
            --bg-reveal: #0a0a0c;
            --card-bg: #111116;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', sans-serif; }

        body {
            background-color: var(--bg-dark);
            color: #ccc;
            transition: background-color 1.5s ease;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            overflow-x: hidden;
        }

        /* --- THE INTERACTIVE LAMP --- */
        .lamp-box {
            position: fixed;
            top: 0;
            z-index: 100;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: transform 1.2s ease-in-out;
        }

        body.on .lamp-box { transform: translateY(-420px); }

        .cord-wire { width: 2px; height: 100px; background: #333; }
        
        .lamp-shade {
            width: 150px; height: 80px;
            background: var(--lamp-body);
            clip-path: polygon(20% 0%, 80% 0%, 100% 100%, 0% 100%);
            border-bottom: 3px solid #333;
        }

        .pull-thread {
            width: 4px; height: 200px;
            background: var(--thread-glow);
            cursor: url('https://img.icons8.com/ios-filled/50/ffffff/hand.png'), pointer;
            box-shadow: 0 0 25px var(--thread-glow);
            position: relative;
            transition: height 0.1s;
        }

        .pull-thread::after {
            content: '';
            position: absolute;
            bottom: -20px; left: -8px;
            width: 20px; height: 20px;
            background: var(--thread-glow);
            border-radius: 50%;
            box-shadow: 0 0 20px var(--thread-glow);
        }

        /* --- CONTENT & STEP-BY-STEP LINKS --- */
        .curriculum {
            opacity: 0;
            visibility: hidden;
            max-width: 800px;
            padding: 60px 20px;
            transition: opacity 1.5s ease 0.5s;
        }

        body.on .curriculum { opacity: 1; visibility: visible; }

        h1 { font-size: 2.8rem; color: #fff; margin-bottom: 10px; text-align: center; }
        .intro-text { text-align: center; margin-bottom: 40px; color: var(--accent-purple); }

        .step-card {
            background: var(--card-bg);
            border: 1px solid #222;
            padding: 30px;
            border-radius: 20px;
            margin-bottom: 25px;
            transition: 0.3s;
        }

        .step-card:hover { border-color: var(--accent-purple); }

        .step-header { display: flex; align-items: center; margin-bottom: 15px; }
        .step-num { 
            background: var(--accent-purple); color: #000; 
            width: 30px; height: 30px; border-radius: 50%; 
            display: grid; place-items: center; font-weight: bold; margin-right: 15px;
        }

        .step-card p { line-height: 1.6; margin-bottom: 20px; font-size: 1rem; }

        /* Inline Action Links */
        .action-link {
            display: inline-flex;
            align-items: center;
            color: var(--accent-purple);
            text-decoration: none;
            font-weight: bold;
            border: 1px solid var(--accent-purple);
            padding: 8px 16px;
            border-radius: 8px;
            transition: 0.3s;
        }

        .action-link:hover {
            background: var(--accent-purple);
            color: #000;
        }

        .action-link::after { content: ' →'; margin-left: 8px; }

    </style>
</head>
<body>

    <div class="lamp-box">
        <div class="cord-wire"></div>
        <div class="lamp-shade"></div>
        <div class="pull-thread" id="trigger"></div>
    </div>

    <div class="curriculum">
        <h1>AI-Powered Web Launch
            by mastering skillz
        </h1>
        <p class="intro-text">The lamp is gone. Your future as a creator begins now.</p>

        <div class="step-card">
            <div class="step-header">
                <div class="step-num">1</div>
                <h3>Generate Your Code</h3>
            </div>
            <p>Don't spend weeks learning syntax. Ask an AI to build your vision. Use a prompt like: <i>"Write a professional HTML/CSS code for a single-page student portfolio with a glassmorphism style."</i></p>
            <a href="https://gemini.google.com" target="_blank" class="action-link">Start Prompting with Gemini</a>
        </div>

        <div class="step-card">
            <div class="step-header">
                <div class="step-num">2</div>
                <h3>Setup Your Cloud Storage</h3>
            </div>
            <p>Every developer needs a GitHub account. This is where your code lives safely in the "cloud" so you never lose it and can show it to employers later.</p>
            <a href="https://github.com/join" target="_blank" class="action-link">Create Your GitHub Account</a>
        </div>

        <div class="step-card">
            <div class="step-header">
                <div class="step-num">3</div>
                <h3>Create a Repository</h3>
            </div>
            <p>A "Repository" is just a fancy word for your project folder on GitHub. Create one named <b>'my-website'</b> to hold your AI-generated files.</p>
            <a href="https://github.com/new" target="_blank" class="action-link">Initialize New Repository</a>
        </div>

        <div class="step-card">
            <div class="step-header">
                <div class="step-num">4</div>
                <h3>Upload & Deploy</h3>
            </div>
            <p>Upload your <code>index.html</code>. Once uploaded, go to <b>Settings > Pages</b> to turn your code into a live website. Need a visual guide on how to click those buttons?</p>
            <a href="https://pages.github.com/" target="_blank" class="action-link">View Hosting Guide</a>
        </div>
    </div>

    <script>
        const trigger = document.getElementById('trigger');
        const body = document.body;

        trigger.addEventListener('click', () => {
            body.classList.add('on');
            body.style.backgroundColor = "var(--bg-reveal)";
        });
    </script>
</body>
</html>
