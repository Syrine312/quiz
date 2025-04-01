<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Test de Personnalité - Ennéagramme</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }
        
        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        
        h1 {
            text-align: center;
            color: white;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .question {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .question h3 {
            font-size: 20px;
            margin-top: 0;
            color: #16385a;
        }
        
        .options {
            display: grid;
            grid-template-columns: 1fr;
            gap: 10px;
        }
        
        .option {
            font-size: 18px;
            padding: 12px 15px;
            border: 1px solid rgba(0,0,0,0.1);
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            background-color: rgba(255,255,255,0.8);
        }
        
        .option:hover {
            background-color: rgba(227, 242, 253, 0.9);
            transform: translateY(-2px);
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .option.selected {
            background-color: #e3f2fd;
            border-color: #2196f3;
            box-shadow: 0 0 0 2px rgba(33, 150, 243, 0.3);
        }
        
        button {
            display: block;
            width: 100%;
            padding: 15px;
            background-color: #2196f3;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s;
            font-weight: bold;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        button:hover {
            background-color: #0d8bf2;
            transform: translateY(-2px);
            box-shadow: 0 6px 8px rgba(0,0,0,0.15);
        }
        
        .result {
            display: none;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 8px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            text-align: center;
            position: relative;
            z-index: 10;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
            animation: fadeIn 0.5s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .result h2 {
            color: #2c3e50;
            margin-top: 0;
            font-size: 28px;
        }
        
        .result-emoji {
            font-size: 60px;
            margin-bottom: 20px;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        .result-description {
            text-align: left;
            margin-top: 20px;
            font-size: 18px;
            line-height: 1.7;
        }
        
        .progress-container {
            width: 100%;
            background-color: rgba(255,255,255,0.3);
            border-radius: 5px;
            margin: 20px 0;
            overflow: hidden;
        }
        
        .progress-bar {
            height: 10px;
            background: linear-gradient(90deg, #4caf50, #8bc34a);
            border-radius: 5px;
            width: 0%;
            transition: width 0.5s;
        }
        
        .progress-text {
            text-align: center;
            margin-bottom: 10px;
            font-size: 16px;
            color: white;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
        }
        
        .navigation-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 25px;
            gap: 15px;
        }
        
        .navigation-buttons button {
            width: 100%;
            padding: 14px;
            margin-top: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }
        
        #prev-btn {
            background: linear-gradient(135deg, #9c27b0, #673ab7);
            box-shadow: 0 4px 8px rgba(156, 39, 176, 0.3);
        }
        
        #prev-btn:hover {
            background: linear-gradient(135deg, #8e24aa, #5e35b1);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(156, 39, 176, 0.4);
        }
        
        #next-btn {
            background: linear-gradient(135deg, #ff5722, #ff9800);
            box-shadow: 0 4px 8px rgba(255, 87, 34, 0.3);
        }
        
        #next-btn:hover {
            background: linear-gradient(135deg, #f4511e, #fb8c00);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(255, 87, 34, 0.4);
        }
        
        #submit-btn {
            background: linear-gradient(135deg, #4caf50, #8bc34a);
            box-shadow: 0 4px 8px rgba(76, 175, 80, 0.3);
        }
        
        #submit-btn:hover {
            background: linear-gradient(135deg, #43a047, #7cb342);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(76, 175, 80, 0.4);
        }
        
        /* Animation avion */
        .airplane {
            position: absolute;
            right: -200px;
            top: 30%;
            width: 150px;
            height: 150px;
            z-index: 5;
            display: none;
            animation: fly 8s linear forwards;
        }
        
        @keyframes fly {
            0% {
                transform: translateX(0) translateY(0) rotate(0deg);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            80% {
                opacity: 1;
            }
            100% {
                transform: translateX(-1500px) translateY(-100px) rotate(-10deg);
                opacity: 0;
            }
        }
        
        /* Bulles flottantes */
        .bubble {
            position: absolute;
            background-color: rgba(255,255,255,0.15);
            border-radius: 50%;
            animation: float linear infinite;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Bouton recommencer */
        #restart-btn {
            background: linear-gradient(135deg, #9c27b0, #673ab7);
            margin-top: 30px;
            box-shadow: 0 4px 8px rgba(156, 39, 176, 0.3);
            display: none; /* Caché par défaut */
        }
        
        #restart-btn:hover {
            background: linear-gradient(135deg, #8e24aa, #5e35b1);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(156, 39, 176, 0.4);
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Bulles flottantes -->
    <div id="bubbles-container"></div>
    
    <!-- Avion pour l'animation des résultats -->
    <img src="https://cdn-icons-png.flaticon.com/512/1047/1047711.png" class="airplane" id="airplane">
    
    <h1>Test de Personnalité - Ennéagramme</h1>
    
    <div id="quiz-container">
        <div class="progress-text">Question <span id="current-question">1</span>/10</div>
        <div class="progress-container">
            <div class="progress-bar" id="progress-bar"></div>
        </div>
        
        <div id="questions-container"></div>
        
        <div class="navigation-buttons">
            <button id="prev-btn"><i class="fas fa-arrow-left button-icon"></i> Précédent</button>
            <button id="next-btn">Suivant <i class="fas fa-arrow-right button-icon"></i></button>
        </div>
        
        <button id="submit-btn"><i class="fas fa-star button-icon"></i> Voir mes résultats</button>
    </div>
    
    <div id="result-container" class="result">
        <div class="result-emoji" id="result-emoji"></div>
        <h2 id="result-title"></h2>
        <div class="result-description" id="result-description"></div>
    </div>
    
    <!-- Bouton reprendre le quiz -->
    <button id="restart-btn"><i class="fas fa-redo button-icon"></i> Reprendre le quiz</button>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Créer des bulles flottantes
            function createBubbles() {
                const container = document.getElementById('bubbles-container');
                for (let i = 0; i < 20; i++) {
                    const bubble = document.createElement('div');
                    bubble.classList.add('bubble');
                    
                    // Taille aléatoire entre 10 et 50px
                    const size = Math.random() * 40 + 10;
                    bubble.style.width = `${size}px`;
                    bubble.style.height = `${size}px`;
                    
                    // Position aléatoire
                    bubble.style.left = `${Math.random() * 100}%`;
                    bubble.style.bottom = `-${size}px`;
                    
                    // Durée d'animation aléatoire
                    const duration = Math.random() * 20 + 10;
                    bubble.style.animationDuration = `${duration}s`;
                    
                    // Délai aléatoire
                    bubble.style.animationDelay = `${Math.random() * 10}s`;
                    
                    container.appendChild(bubble);
                }
            }
            
            createBubbles();

            const questions = [
                {
                    question: "1. Quelle phrase vous correspond le plus ?",
                    options: [
                        { text: "A) « Je veux que tout soit parfait. »", value: "A" },
                        { text: "B) « J'aime aider et être apprécié(e). »", value: "B" },
                        { text: "C) « Je veux réussir et être reconnu(e). »", value: "C" },
                        { text: "D) « Je veux être unique et spécial(e). »", value: "D" },
                        { text: "E) « J'ai besoin de comprendre avant d'agir. »", value: "E" },
                        { text: "F) « Je cherche avant tout la sécurité et la stabilité. »", value: "F" },
                        { text: "G) « Je veux profiter de la vie et éviter les contraintes. »", value: "G" },
                        { text: "H) « J'aime diriger et prendre des décisions. »", value: "H" },
                        { text: "I) « Je veux l'harmonie et éviter les conflits. »", value: "I" }
                    ]
                },
                {
                    question: "2. Comment réagissez-vous face à un défi ?",
                    options: [
                        { text: "A) Je m'assure que tout soit fait à la perfection.", value: "A" },
                        { text: "B) Je veux que tout le monde soit bien et en accord.", value: "B" },
                        { text: "C) Je cherche la stratégie gagnante pour réussir.", value: "C" },
                        { text: "D) Je me demande comment le rendre unique et créatif.", value: "D" },
                        { text: "E) Je réfléchis longuement avant d'agir.", value: "E" },
                        { text: "F) J'évalue les risques avant de me lancer.", value: "F" },
                        { text: "G) J'essaie d'en tirer du plaisir et de m'amuser.", value: "G" },
                        { text: "H) Je prends le contrôle de la situation.", value: "H" },
                        { text: "I) J'essaie d'éviter les conflits et de calmer tout le monde.", value: "I" }
                    ]
                },
                {
                    question: "3. Dans un groupe, quel rôle prenez-vous naturellement ?",
                    options: [
                        { text: "A) Celui qui fixe des règles et cherche la perfection.", value: "A" },
                        { text: "B) Celui qui soutient et aide les autres.", value: "B" },
                        { text: "C) Celui qui motive et pousse tout le monde vers la réussite.", value: "C" },
                        { text: "D) Celui qui exprime ses idées et émotions.", value: "D" },
                        { text: "E) Celui qui observe et analyse avant d'agir.", value: "E" },
                        { text: "F) Celui qui veut que tout soit sécurisé et stable.", value: "F" },
                        { text: "G) Celui qui cherche à détendre l'ambiance et à s'amuser.", value: "G" },
                        { text: "H) Celui qui prend la tête du groupe et donne des directives.", value: "H" },
                        { text: "I) Celui qui cherche à apaiser les tensions et à harmoniser le groupe.", value: "I" }
                    ]
                },
                {
                    question: "4. Face à un problème, quelle est votre approche ?",
                    options: [
                        { text: "A) Trouver la solution parfaite, sans erreur.", value: "A" },
                        { text: "B) Chercher à aider et à faire plaisir aux autres.", value: "B" },
                        { text: "C) Aller droit au but et réussir à tout prix.", value: "C" },
                        { text: "D) Suivre mon instinct et mes émotions.", value: "D" },
                        { text: "E) Analyser toutes les données avant d'agir.", value: "E" },
                        { text: "F) Choisir la solution la plus sécurisante.", value: "F" },
                        { text: "G) Trouver la solution la plus agréable et éviter le stress.", value: "G" },
                        { text: "H) Prendre des décisions rapidement et imposer une solution.", value: "H" },
                        { text: "I) Chercher une solution qui contente tout le monde.", value: "I" }
                    ]
                },
                {
                    question: "5. Quel mot vous définit le mieux ?",
                    options: [
                        { text: "A) Exigeant(e).", value: "A" },
                        { text: "B) Généreux(se).", value: "B" },
                        { text: "C) Ambitieux(se).", value: "C" },
                        { text: "D) Sensible.", value: "D" },
                        { text: "E) Curieux(se).", value: "E" },
                        { text: "F) Loyal(e).", value: "F" },
                        { text: "G) Optimiste.", value: "G" },
                        { text: "H) Déterminé(e).", value: "H" },
                        { text: "I) Diplomate.", value: "I" }
                    ]
                },
                {
                    question: "6. Quelle est votre plus grande peur ?",
                    options: [
                        { text: "A) Faire une erreur.", value: "A" },
                        { text: "B) Ne pas être aimé(e).", value: "B" },
                        { text: "C) Échouer.", value: "C" },
                        { text: "D) Être banal.", value: "D" },
                        { text: "E) Être ignoré(e).", value: "E" },
                        { text: "F) Être en insécurité.", value: "F" },
                        { text: "G) Être enfermé(e) dans une routine.", value: "G" },
                        { text: "H) Perdre le contrôle.", value: "H" },
                        { text: "I) Le conflit.", value: "I" }
                    ]
                },
                {
                    question: "7. Quel métier vous attire le plus ?",
                    options: [
                        { text: "A) Juge ou expert.", value: "A" },
                        { text: "B) Médecin ou travailleur social.", value: "B" },
                        { text: "C) Entrepreneur ou sportif de haut niveau.", value: "C" },
                        { text: "D) Artiste ou écrivain.", value: "D" },
                        { text: "E) Chercheur ou philosophe.", value: "E" },
                        { text: "F) Policier ou fonctionnaire.", value: "F" },
                        { text: "G) Voyageur ou créateur de contenu.", value: "G" },
                        { text: "H) PDG ou militaire.", value: "H" },
                        { text: "I) Coach ou médiateur.", value: "I" }
                    ]
                },
                {
                    question: "8. Quelle est votre plus grande qualité ?",
                    options: [
                        { text: "A) Mon sens du détail.", value: "A" },
                        { text: "B) Mon altruisme.", value: "B" },
                        { text: "C) Ma motivation.", value: "C" },
                        { text: "D) Ma créativité.", value: "D" },
                        { text: "E) Mon intelligence.", value: "E" },
                        { text: "F) Ma fidélité.", value: "F" },
                        { text: "G) Mon enthousiasme.", value: "G" },
                        { text: "H) Mon leadership.", value: "H" },
                        { text: "I) Ma diplomatie.", value: "I" }
                    ]
                },
                {
                    question: "9. Quel est votre plus grand défaut ?",
                    options: [
                        { text: "A) Je suis trop perfectionniste.", value: "A" },
                        { text: "B) Je m'oublie pour les autres.", value: "B" },
                        { text: "C) Je suis obsédé(e) par la réussite.", value: "C" },
                        { text: "D) Je suis hypersensible.", value: "D" },
                        { text: "E) Je suis distant(e) et réservé(e).", value: "E" },
                        { text: "F) Je suis anxieux(se).", value: "F" },
                        { text: "G) Je fuis les responsabilités.", value: "G" },
                        { text: "H) Je suis trop autoritaire.", value: "H" },
                        { text: "I) Je suis indécis(e).", value: "I" }
                    ]
                },
                {
                    question: "10. Comment prenez-vous une décision importante ?",
                    options: [
                        { text: "A) Je réfléchis longtemps pour ne pas faire d'erreur.", value: "A" },
                        { text: "B) Je consulte mes proches pour être sûr(e).", value: "B" },
                        { text: "C) Je choisis ce qui me mènera au succès.", value: "C" },
                        { text: "D) Je me fie à mon intuition et à mes émotions.", value: "D" },
                        { text: "E) Je collecte un maximum d'informations.", value: "E" },
                        { text: "F) Je cherche ce qui est le plus sûr.", value: "F" },
                        { text: "G) Je suis impulsif(ve) et je me lance.", value: "G" },
                        { text: "H) Je prends rapidement les choses en main.", value: "H" },
                        { text: "I) J'essaie d'harmoniser tous les avis.", value: "I" }
                    ]
                }
            ];

            const results = {
                "A": {
                    title: "Le Perfectionniste 🎯",
                    emoji: "🎯",
                    description: "Vous aimez que tout soit bien fait et vous vous imposez des standards élevés. Votre rigueur est un atout !"
                },
                "B": {
                    title: "L'Altruiste 💖",
                    emoji: "💖",
                    description: "Vous êtes bienveillant(e) et aimez aider les autres. Vous cherchez l'harmonie dans vos relations."
                },
                "C": {
                    title: "Le Battant 🏆",
                    emoji: "🏆",
                    description: "Vous êtes motivé(e) par la réussite et aimez relever des défis. Vous aimez l'action et l'efficacité."
                },
                "D": {
                    title: "Le Romantique 🎭",
                    emoji: "🎭",
                    description: "Vous ressentez un besoin d'authenticité et d'unicité. Vous aimez exprimer votre créativité et vos émotions."
                },
                "E": {
                    title: "L'Observateur 🔍",
                    emoji: "🔍",
                    description: "Vous êtes curieux(se) et avez besoin de comprendre avant d'agir. Vous aimez l'analyse et la réflexion."
                },
                "F": {
                    title: "Le Loyaliste 🔒",
                    emoji: "🔒",
                    description: "Vous recherchez la sécurité et la stabilité. Vous êtes une personne fiable sur qui on peut compter."
                },
                "G": {
                    title: "L'Épicurien 🌈",
                    emoji: "🌈",
                    description: "Vous aimez la liberté et profitez pleinement de la vie. Vous fuyez les contraintes et cherchez toujours le positif."
                },
                "H": {
                    title: "Le Leader 🚀",
                    emoji: "🚀",
                    description: "Vous aimez prendre des décisions et avoir le contrôle des situations. Vous êtes un(e) meneur(se) naturel(le)."
                },
                "I": {
                    title: "Le Médiateur 🕊",
                    emoji: "🕊",
                    description: "Vous cherchez l'harmonie et évitez les conflits. Vous aimez la paix et la tranquillité."
                }
            };

            const questionsContainer = document.getElementById('questions-container');
            const submitBtn = document.getElementById('submit-btn');
            const resultContainer = document.getElementById('result-container');
            const resultTitle = document.getElementById('result-title');
            const resultEmoji = document.getElementById('result-emoji');
            const resultDescription = document.getElementById('result-description');
            const currentQuestionSpan = document.getElementById('current-question');
            const progressBar = document.getElementById('progress-bar');
            const prevBtn = document.getElementById('prev-btn');
            const nextBtn = document.getElementById('next-btn');
            const airplane = document.getElementById('airplane');
            const restartBtn = document.getElementById('restart-btn');
            const quizContainer = document.getElementById('quiz-container');

            let answers = {};
            let currentQuestion = 0;

            function updateNavigationButtons() {
                prevBtn.style.display = currentQuestion === 0 ? 'none' : 'block';
                nextBtn.style.display = currentQuestion === questions.length - 1 ? 'none' : 'block';
                submitBtn.style.display = currentQuestion === questions.length - 1 ? 'block' : 'none';
            }

            function renderQuestion(index) {
                currentQuestion = index;
                currentQuestionSpan.textContent = index + 1;
                progressBar.style.width = `${(index + 1) * 10}%`;
                
                const question = questions[index];
                let optionsHTML = question.options.map(option => `
                    <div class="option" data-value="${option.value}">
                        ${option.text}
                    </div>
                `).join('');

                questionsContainer.innerHTML = `
                    <div class="question">
                        <h3>${question.question}</h3>
                        <div class="options">${optionsHTML}</div>
                    </div>
                `;

                // Select previously chosen option if exists
                if (answers[index] !== undefined) {
                    const options = document.querySelectorAll('.option');
                    options.forEach(opt => {
                        if (opt.dataset.value === answers[index]) {
                            opt.classList.add('selected');
                        }
                    });
                }

                // Add event listeners to options
                document.querySelectorAll('.option').forEach(option => {
                    option.addEventListener('click', function() {
                        // Remove selected class from all options in this question
                        document.querySelectorAll('.option').forEach(opt => {
                            opt.classList.remove('selected');
                        });
                        
                        // Add selected class to clicked option
                        this.classList.add('selected');
                        
                        // Save answer
                        answers[index] = this.dataset.value;
                    });
                });

                updateNavigationButtons();
            }

            function calculateResult() {
                const counts = {};
                
                // Initialize counts
                for (let key in results) {
                    counts[key] = 0;
                }
                
                // Count answers
                for (let answer in answers) {
                    const value = answers[answer];
                    counts[value]++;
                }
                
                // Find max count
                let maxCount = 0;
                let resultKey = 'A';
                
                for (let key in counts) {
                    if (counts[key] > maxCount) {
                        maxCount = counts[key];
                        resultKey = key;
                    }
                }
                
                return resultKey;
            }

            function showResult(resultKey) {
                // Animation avion
                airplane.style.display = 'block';
                airplane.style.top = `${Math.random() * 50 + 20}%`;
                airplane.style.animation = 'none';
                airplane.offsetHeight; // Trigger reflow
                airplane.style.animation = 'fly 8s linear forwards';
                
                // Changement de fond
                document.body.style.background = 'linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a6c1ee)';
                document.body.style.backgroundSize = '400% 400%';
                
                // Afficher le résultat après un délai
                setTimeout(() => {
                    const result = results[resultKey];
                    resultTitle.textContent = result.title;
                    resultEmoji.textContent = result.emoji;
                    resultDescription.textContent = result.description;
                    
                    quizContainer.style.display = 'none';
                    resultContainer.style.display = 'block';
                    restartBtn.style.display = 'block'; // Afficher le bouton reprendre
                }, 2000);
            }

            function restartQuiz() {
                // Réinitialiser les réponses
                answers = {};
                currentQuestion = 0;
                
                // Réinitialiser l'affichage
                document.body.style.background = 'linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab)';
                document.body.style.backgroundSize = '400% 400%';
                
                // Cacher le résultat et le bouton reprendre, afficher le quiz
                resultContainer.style.display = 'none';
                restartBtn.style.display = 'none';
                quizContainer.style.display = 'block';
                
                // Recharger la première question
                renderQuestion(0);
            }

            // Initialize quiz
            renderQuestion(0);
            updateNavigationButtons();
            restartBtn.style.display = 'none'; // Cacher le bouton au démarrage

            // Navigation buttons events
            prevBtn.addEventListener('click', function() {
                if (currentQuestion > 0) {
                    currentQuestion--;
                    renderQuestion(currentQuestion);
                }
            });

            nextBtn.addEventListener('click', function() {
                if (currentQuestion < questions.length - 1) {
                    // Vérifier qu'une réponse a été sélectionnée
                    if (answers[currentQuestion] === undefined) {
                        alert("Veuillez sélectionner une réponse avant de continuer.");
                        return;
                    }
                    currentQuestion++;
                    renderQuestion(currentQuestion);
                }
            });

            // Submit button event listener
            submitBtn.addEventListener('click', function() {
                // Check if all questions are answered
                if (Object.keys(answers).length !== questions.length) {
                    alert("Veuillez répondre à toutes les questions avant de soumettre.");
                    return;
                }
                
                const result = calculateResult();
                showResult(result);
            });

            // Restart button event listener
            restartBtn.addEventListener('click', restartQuiz);

            // Navigation with keyboard arrows
            document.addEventListener('keydown', function(e) {
                if (e.key === 'ArrowRight' && currentQuestion < questions.length - 1) {
                    if (answers[currentQuestion] !== undefined) {
                        currentQuestion++;
                        renderQuestion(currentQuestion);
                    } else {
                        alert("Veuillez sélectionner une réponse avant de continuer.");
                    }
                } else if (e.key === 'ArrowLeft' && currentQuestion > 0) {
                    currentQuestion--;
                    renderQuestion(currentQuestion);
                }
            });
        });
    </script>
</body>
</html>
