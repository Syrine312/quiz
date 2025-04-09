
<html >
<head>
    
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
                    question: "1. Si tu étais un super-héros, quel pouvoir choisirais-tu ?",
                    options: [
                        { text: "A) «  Être parfait dans tout ce que je fais. »", value: "A" },
                        { text: "B) «  Soigner les autres avec mes mains.. »", value: "B" },
                        { text: "C) « Courir à une vitesse incroyable pour tout accomplir. »", value: "C" },
                        { text: "D) «  Créer des illusions magnifiques. »", value: "D" },
                        { text: "E) «Lire dans les pensées. »", value: "E" },
                        { text: "F) « Prévoir l’avenir pour éviter les dangers. »", value: "F" },
                        { text: "G) « Voyager dans le monde en un claquement de doigt. »", value: "G" },
                        { text: "H) «  Contrôler les éléments (feu, vent, etc...). »", value: "H" },
                        { text: "I) « Calmer instantanément les conflits. »", value: "I" }
                    ]
                },
                {
                    question: "2. Ta façon préférée de passer une journée libre ?",
                    options: [
                        { text: "A)  Ranger, organiser ou planifier à l’avance.", value: "A" },
                        { text: "B) Faire du bénévolat ou aider un proche.", value: "B" },
                        { text: "C) Travailler sur un projet personnel ambitieux.", value: "C" },
                        { text: "D) Écrire, dessiner ou écouter de la musique profonde.", value: "D" },
                        { text: "E) Lire, regarder un documentaire ou apprendre quelque chose.", value: "E" },
                        { text: "F) Rester à la maison, bien au chaud, dans ma routine.", value: "F" },
                        { text: "G) Sortir, explorer de nouveaux endroits ou improviser.", value: "G" },
                        { text: "H) Gérer un événement ou prendre des décisions.", value: "H" },
                        { text: "I) Être avec des gens sans prise de tête, dans la bonne humeur.", value: "I" }
                    ]
                },
                {
                    question: "3. Face à un défi difficile, tu...",
                    options: [
                        { text: "A) Analyses chaque étape pour éviter les erreurs.", value: "A" },
                        { text: "B) Te tournes vers des personnes de confiance.", value: "B" },
                        { text: "C) Te lances sans hésiter, prêt à gagner.", value: "C" },
                        { text: "D) Ressens profondément la situation avant d’agir.", value: "D" },
                        { text: "E)  Cherches toutes les infos avant de choisir.", value: "E" },
                        { text: "F) Évalues les risques et cherches la sécurité.", value: "F" },
                        { text: "G) Te dis que ça va aller, et tu fonces !", value: "G" },
                        { text: "H) Agis rapidement et prends les choses en main.", value: "H" },
                        { text: "I) Essaies d’écouter chacun et trouver un compromis.", value: "I" }
                    ]
                },
                {
                    question: "4. Ta devise de vie pourrait être...",
                    options: [
                        { text: "A) Fais-le bien ou ne le fais pas.", value: "A" },
                        { text: "B) L’amour guérit tout.", value: "B" },
                        { text: "C) Pas de succès sans effort.", value: "C" },
                        { text: "D) Reste fidèle à toi-même.", value: "D" },
                        { text: "E) La connaissance, c’est le pouvoir.", value: "E" },
                        { text: "F) Mieux vaut prévenir que guérir.", value: "F" },
                        { text: "G)  Profite du moment.", value: "G" },
                        { text: "H) Qui commande, gagne.", value: "H" },
                        { text: "I) Vivons en paix, ensemble.", value: "I" }
                    ]
                },
                {
                    question: "5. Quel type de film préfères-tu ?",
                    options: [
                        { text: "A) Un film inspirant avec une belle morale.", value: "A" },
                        { text: "B) Une histoire émouvante pleine de générosité.", value: "B" },
                        { text: "C) Une success story ou un film d’action.", value: "C" },
                        { text: "D) Un drame romantique ou artistique.", value: "D" },
                        { text: "E) Un documentaire captivant.", value: "E" },
                        { text: "F) Un thriller psychologique avec du suspense.", value: "F" },
                        { text: "G) Une comédie pleine d’aventures.", value: "G" },
                        { text: "H) Un film de guerre ou de stratégie.", value: "H" },
                        { text: "I) Un film familial ou feel good.", value: "I" }
                    ]
                },
                {
                    question: "6. Quand tu rencontres quelqu’un de nouveau...",
                    options: [
                        { text: "A) Tu veux faire bonne impression immédiatement.", value: "A" },
                        { text: "B) Tu es attentionné(e) et à l’écoute.", value: "B" },
                        { text: "C) Tu cherches à te démarquer et montrer tes réussites.", value: "C" },
                        { text: "D) Tu observes leur profondeur émotionnelle.", value: "D" },
                        { text: "E) Tu poses des questions pour mieux les comprendre.", value: "E" },
                        { text: "F) Tu restes prudent(e), tu observes d’abord.", value: "F" },
                        { text: "G) Tu rigoles facilement.", value: "G" },
                        { text: "H) Tu diriges la conversation.", value: "H" },
                        { text: "I) Tu fais tout pour que tout le monde se sente à l’aise.", value: "I" }
                    ]
                },
                {
                    question: "7. Si tu étais un animal, tu serais...",
                     options: [
                        { text: "A) Une fourmi.", value: "A" },
                        { text: "B) Un chien.", value: "B" },
                        { text: "C)  Un tigre.", value: "C" },
                        { text: "D)  Un cygne.", value: "D" },
                        { text: "E)Un hibou.", value: "E" },
                        { text: "F)  Une tortue.", value: "F" },
                        { text: "G) Un singe.", value: "G" },
                        { text: "H) Un aigle.", value: "H" },
                        { text: "I) Un panda.", value: "I" }
                    ]
                },
                {
                    question: "8. Quelle qualité te décrit le mieux ?", 
                    options: [
                        { text: "A) La rigueur.", value: "A" },
                        { text: "B) La générosité.", value: "B" },
                        { text: "C) L’énergie.", value: "C" },
                        { text: "D) La sensibilité.", value: "D" },
                        { text: "E) L’intelligence.", value: "E" },
                        { text: "F)  La loyauté.", value: "F" },
                        { text: "G) La joie.", value: "G" },
                        { text: "H) L’assurance.", value: "H" },
                        { text: "I)  L’harmonie.", value: "I" }
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
                    question: "10. Ta plus grande motivation, c’est..." ,
                    options: [
                        { text: "A) Bien faire et être respecté(e).", value: "A" },
                        { text: "B) Être utile aux autres.", value: "B" },
                        { text: "C) Réussir et être reconnu(e).", value: "C" },
                        { text: "D) Vivre une vie pleine de sens.", value: "D" },
                        { text: "E) Savoir et comprendre.", value: "E" },
                        { text: "F)  Se sentir en sécurité.", value: "F" },
                        { text: "G) Être libre et heureux(se).", value: "G" },
                        { text: "H) Avoir de l’influence.", value: "H" },
                        { text: "I) Vivre en paix avec les autres.", value: "I" }
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
