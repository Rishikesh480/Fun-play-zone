# Fun-play-zone <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fun & Play Zone</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #f72585;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f8961e;
            --danger: #ef233c;
            --card-bg: rgba(255, 255, 255, 0.9);
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: var(--light);
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
            position: relative;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }
        
        /* Header Styles */
        header {
            text-align: center;
            padding: 30px 20px;
            margin-bottom: 30px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: var(--shadow);
            animation: fadeIn 1s ease;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .logo i {
            font-size: 3rem;
            color: var(--accent);
        }
        
        .logo h1 {
            font-size: 2.5rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.2);
        }
        
        .tagline {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 20px;
            color: rgba(255, 255, 255, 0.9);
        }
        
        /* Navigation */
        nav {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
        }
        
        .nav-btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1rem;
            box-shadow: 0 4px 15px rgba(247, 37, 133, 0.3);
        }
        
        .nav-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(247, 37, 133, 0.4);
        }
        
        /* Main Content */
        .content-section {
            display: none;
            background: var(--card-bg);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: var(--shadow);
            animation: slideUp 0.5s ease;
        }
        
        .active {
            display: block;
        }
        
        .section-title {
            color: var(--secondary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid var(--accent);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* Home Page */
        .welcome-section {
            text-align: center;
            padding: 20px;
            margin-bottom: 30px;
            border-radius: 15px;
            background: linear-gradient(135deg, rgba(67, 97, 238, 0.3) 0%, rgba(63, 55, 201, 0.3) 100%);
        }
        
        .welcome-section h2 {
            font-size: 2rem;
            margin-bottom: 15px;
        }
        
        .featured-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .feature-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
            box-shadow: var(--shadow);
            color: var(--dark);
            cursor: pointer;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .feature-icon {
            font-size: 3.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .feature-card h3 {
            margin-bottom: 10px;
            color: var(--secondary);
        }
        
        /* Games */
        .games-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .game-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
        }
        
        .game-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }
        
        .game-img {
            height: 180px;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
        }
        
        .game-content {
            padding: 20px;
        }
        
        .game-content h3 {
            color: var(--secondary);
            margin-bottom: 10px;
        }
        
        .play-btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 15px;
            width: 100%;
            transition: all 0.3s ease;
        }
        
        .play-btn:hover {
            background: var(--primary);
        }
        
        /* Meme Generator */
        .meme-generator {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: var(--shadow);
            color: var(--dark);
        }
        
        .meme-preview {
            background: #f0f2f5;
            height: 300px;
            border-radius: 10px;
            margin: 20px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        
        .meme-text {
            position: absolute;
            width: 100%;
            text-align: center;
            color: white;
            font-weight: bold;
            text-shadow: 2px 2px 0 #000, -2px -2px 0 #000, 2px -2px 0 #000, -2px 2px 0 #000;
            font-size: 2.5rem;
            font-family: Impact, sans-serif;
            padding: 10px;
        }
        
        .top-text {
            top: 10px;
        }
        
        .bottom-text {
            bottom: 10px;
        }
        
        .meme-controls {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        
        .meme-controls input {
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
        }
        
        .meme-controls button {
            grid-column: span 2;
            background: var(--primary);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .meme-controls button:hover {
            background: var(--secondary);
        }
        
        /* Quizzes */
        .quiz-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            color: var(--dark);
        }
        
        .quiz-card h3 {
            color: var(--secondary);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .quiz-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 0.9rem;
            color: #666;
        }
        
        .start-btn {
            background: var(--success);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
        }
        
        .start-btn:hover {
            background: #3ab0d6;
        }
        
        /* Jokes */
        .joke-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            color: var(--dark);
            position: relative;
        }
        
        .joke-card:before {
            content: """;
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 5rem;
            color: rgba(247, 37, 133, 0.1);
            font-family: serif;
        }
        
        .joke-text {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 20px;
        }
        
        .new-joke-btn {
            background: var(--warning);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .new-joke-btn:hover {
            background: #e08a1a;
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 30px 0;
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0;
        }
        
        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            color: var(--accent);
            transform: scale(1.2);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideUp {
            from { 
                opacity: 0;
                transform: translateY(20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .logo h1 {
                font-size: 2rem;
            }
            
            .nav-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
            
            .featured-grid {
                grid-template-columns: 1fr;
            }
            
            .meme-controls {
                grid-template-columns: 1fr;
            }
            
            .meme-controls button {
                grid-column: span 1;
            }
        }
        
        /* Decorative Elements */
        .bubble {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            z-index: 1;
        }
        
        .bubble:nth-child(1) {
            width: 150px;
            height: 150px;
            top: 10%;
            left: 5%;
        }
        
        .bubble:nth-child(2) {
            width: 200px;
            height: 200px;
            bottom: 15%;
            right: 10%;
        }
        
        .bubble:nth-child(3) {
            width: 100px;
            height: 100px;
            top: 40%;
            right: 20%;
        }
    </style>
</head>
<body>
    <!-- Decorative bubbles -->
    <div class="bubble"></div>
    <div class="bubble"></div>
    <div class="bubble"></div>
    
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-gamepad"></i>
                <h1>Fun & Play Zone</h1>
            </div>
            <p class="tagline">Play. Laugh. Challenge Your Mind.</p>
            <button class="auth-button sign-in">
                <i class="fab fa-google"></i> Sign In with Google
            </button>
        </header>
        
        <nav>
            <button class="nav-btn" onclick="showSection('home')">
                <i class="fas fa-home"></i> Home
            </button>
            <button class="nav-btn" onclick="showSection('games')">
                <i class="fas fa-dice"></i> Games
            </button>
            <button class="nav-btn" onclick="showSection('quizzes')">
                <i class="fas fa-question-circle"></i> Quizzes
            </button>
            <button class="nav-btn" onclick="showSection('memes')">
                <i class="fas fa-laugh-squint"></i> Memes
            </button>
            <button class="nav-btn" onclick="showSection('jokes')">
                <i class="fas fa-joke"></i> Jokes
            </button>
        </nav>
        
        <!-- Home Section -->
        <section id="home" class="content-section active">
            <div class="welcome-section">
                <h2>Welcome to Fun & Play Zone!</h2>
                <p>Discover endless fun with our collection of games, quizzes, memes, and jokes.</p>
            </div>
            
            <h2 class="section-title">
                <i class="fas fa-star"></i> Featured Activities
            </h2>
            
            <div class="featured-grid">
                <div class="feature-card" onclick="showSection('games')">
                    <div class="feature-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <h3>Mini Games</h3>
                    <p>Enjoy classic games like Tic-Tac-Toe, Memory, and more!</p>
                </div>
                
                <div class="feature-card" onclick="showSection('quizzes')">
                    <div class="feature-icon">
                        <i class="fas fa-puzzle-piece"></i>
                    </div>
                    <h3>Quizzes & Trivia</h3>
                    <p>Test your knowledge with our fun and challenging quizzes.</p>
                </div>
                
                <div class="feature-card" onclick="showSection('memes')">
                    <div class="feature-icon">
                        <i class="fas fa-laugh-beam"></i>
                    </div>
                    <h3>Meme Generator</h3>
                    <p>Create hilarious memes and share them with friends.</p>
                </div>
            </div>
            
            <h2 class="section-title">
                <i class="fas fa-laugh"></i> Daily Fun
            </h2>
            
            <div class="featured-grid">
                <div class="feature-card" onclick="showSection('jokes')">
                    <div class="feature-icon">
                        <i class="fas fa-joke"></i>
                    </div>
                    <h3>Joke of the Day</h3>
                    <p>Get your daily dose of laughter with our curated jokes.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-lightbulb"></i>
                    </div>
                    <h3>Fun Facts</h3>
                    <p>Discover amazing and interesting facts every day.</p>
                </div>
                
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-trophy"></i>
                    </div>
                    <h3>Leaderboard</h3>
                    <p>Compete with friends and climb the leaderboard.</p>
                </div>
            </div>
        </section>
        
        <!-- Games Section -->
        <section id="games" class="content-section">
            <h2 class="section-title">
                <i class="fas fa-dice"></i> Our Game Collection
            </h2>
            
            <div class="games-container">
                <div class="game-card">
                    <div class="game-img">
                        <i class="fas fa-times"></i>
                    </div>
                    <div class="game-content">
                        <h3>Tic-Tac-Toe</h3>
                        <p>The classic strategy game for two players. Try to get three in a row!</p>
                        <button class="play-btn">Play Now</button>
                    </div>
                </div>
                
                <div class="game-card">
                    <div class="game-img">
                        <i class="fas fa-brain"></i>
                    </div>
                    <div class="game-content">
                        <h3>Memory Game</h3>
                        <p>Test your memory skills by matching pairs of cards.</p>
                        <button class="play-btn">Play Now</button>
                    </div>
                </div>
                
                <div class="game-card">
                    <div class="game-img">
                        <i class="fas fa-snake"></i>
                    </div>
                    <div class="game-content">
                        <h3>Snake Game</h3>
                        <p>The classic snake game. Eat food and grow without hitting yourself!</p>
                        <button class="play-btn">Play Now</button>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Quizzes Section -->
        <section id="quizzes" class="content-section">
            <h2 class="section-title">
                <i class="fas fa-question-circle"></i> Quizzes & Trivia
            </h2>
            
            <div class="quiz-card">
                <h3><i class="fas fa-film"></i> Movie Trivia Challenge</h3>
                <div class="quiz-info">
                    <span>10 Questions</span>
                    <span>Difficulty: Medium</span>
                </div>
                <p>How well do you know your movies? Test your knowledge of classic and modern films.</p>
                <button class="start-btn">Start Quiz</button>
            </div>
            
            <div class="quiz-card">
                <h3><i class="fas fa-globe-americas"></i> World Geography Quiz</h3>
                <div class="quiz-info">
                    <span>15 Questions</span>
                    <span>Difficulty: Hard</span>
                </div>
                <p>Identify countries, capitals, and landmarks from around the world.</p>
                <button class="start-btn">Start Quiz</button>
            </div>
            
            <div class="quiz-card">
                <h3><i class="fas fa-user-alt"></i> Personality Test</h3>
                <div class="quiz-info">
                    <span>8 Questions</span>
                    <span>Difficulty: Easy</span>
                </div>
                <p>Which famous historical figure matches your personality? Take the quiz to find out!</p>
                <button class="start-btn">Start Quiz</button>
            </div>
        </section>
        
        <!-- Memes Section -->
        <section id="memes" class="content-section">
            <h2 class="section-title">
                <i class="fas fa-laugh-squint"></i> Meme Generator
            </h2>
            
            <div class="meme-generator">
                <div class="meme-preview">
                    <div class="meme-text top-text">WHEN YOU FINISH THE PROJECT</div>
                    <div class="meme-text bottom-text">BUT THE CLIENT WANTS CHANGES</div>
                </div>
                
                <div class="meme-controls">
                    <input type="text" id="top-text" placeholder="Enter top text">
                    <input type="text" id="bottom-text" placeholder="Enter bottom text">
                    <button id="generate-meme">Generate Meme</button>
                </div>
            </div>
            
            <h3 style="margin: 30px 0 15px; color: white;">Popular Meme Templates</h3>
            
            <div class="games-container">
                <div class="game-card">
                    <div class="game-img" style="background: linear-gradient(45deg, #FF9A8B, #FF6B6B);">
                        <i class="fas fa-surprise"></i>
                    </div>
                    <div class="game-content">
                        <h3>Surprised Pikachu</h3>
                        <p>The classic meme for unexpected situations.</p>
                        <button class="play-btn">Use Template</button>
                    </div>
                </div>
                
                <div class="game-card">
                    <div class="game-img" style="background: linear-gradient(45deg, #4FACFE, #00F2FE);">
                        <i class="fas fa-window-maximize"></i>
                    </div>
                    <div class="game-content">
                        <h3>Drake Template</h3>
                        <p>Perfect for showing preferences or rejections.</p>
                        <button class="play-btn">Use Template</button>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Jokes Section -->
        <section id="jokes" class="content-section">
            <h2 class="section-title">
                <i class="fas fa-joke"></i> Joke of the Day
            </h2>
            
            <div class="joke-card">
                <div class="joke-text">
                    Why don't scientists trust atoms?<br>
                    Because they make up everything!
                </div>
                <button class="new-joke-btn">
                    <i class="fas fa-sync-alt"></i> Get New Joke
                </button>
            </div>
            
            <h3 style="margin: 30px 0 15px; color: white;">More Jokes</h3>
            
            <div class="joke-card">
                <div class="joke-text">
                    What's the best thing about Switzerland?<br>
                    I don't know, but the flag is a big plus!
                </div>
            </div>
            
            <div class="joke-card">
                <div class="joke-text">
                    Why did the scarecrow win an award?<br>
                    Because he was outstanding in his field!
                </div>
            </div>
            
            <div class="joke-card">
                <div class="joke-text">
                    Why don't skeletons fight each other?<br>
                    They don't have the guts!
                </div>
            </div>
        </section>
        
        <footer>
            <div class="social-links">
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-tiktok"></i></a>
            </div>
            <p>© 2023 Fun & Play Zone. All rights reserved.</p>
            <p>Made with ❤️ for endless fun and entertainment</p>
        </footer>
    </div>

    <script>
        // Function to switch between sections
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.content-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Show the selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }
        
        // Generate meme function
        document.getElementById('generate-meme').addEventListener('click', function() {
            const topText = document.getElementById('top-text').value || "WHEN YOU FINISH THE PROJECT";
            const bottomText = document.getElementById('bottom-text').value || "BUT THE CLIENT WANTS CHANGES";
            
            document.querySelector('.top-text').textContent = topText.toUpperCase();
            document.querySelector('.bottom-text').textContent = bottomText.toUpperCase();
        });
        
        // New joke functionality
        const jokes = [
            "Why don't scientists trust atoms? Because they make up everything!",
            "What's the best thing about Switzerland? I don't know, but the flag is a big plus!",
            "Why did the scarecrow win an award? Because he was outstanding in his field!",
            "Why don't skeletons fight each other? They don't have the guts!",
            "What do you call a fake noodle? An impasta!",
            "How does a penguin build its house? Igloos it together!",
            "Why did the bicycle fall over? Because it was two-tired!"
        ];
        
        document.querySelector('.new-joke-btn').addEventListener('click', function() {
            const jokeCards = document.querySelectorAll('.joke-card');
            const randomJoke = jokes[Math.floor(Math.random() * jokes.length)];
            jokeCards[0].querySelector('.joke-text').innerHTML = randomJoke.replace('?', '?<br>');
        });
        
        // Sign in button functionality
        document.querySelector('.sign-in').addEventListener('click', function() {
            alert('Sign in functionality would be implemented with Firebase in a full application. For now, enjoy the site as a guest!');
        });
        
        // Play buttons functionality
        document.querySelectorAll('.play-btn').forEach(button => {
            button.addEventListener('click', function() {
                alert('Game would launch in a full implementation. For now, enjoy exploring the site!');
            });
        });
        
        // Quiz buttons functionality
        document.querySelectorAll('.start-btn').forEach(button => {
            button.addEventListener('click', function() {
                alert('Quiz would start in a full implementation. For now, enjoy exploring the site!');
            });
        });
    </script>
</body>
</html>
