<html >
<head>
    <title>Quiz de Personnalité</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0;
        }
        .quiz-container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 100%;
        }
        h1 {
            text-align: center;
            color: #6200ea;
        }
        .question {
            margin-bottom: 20px;
        }
        .question h2 {
            margin-bottom: 10px;
            font-size: 1.2em;
            color: #333;
        }
        .options {
            display: flex;
            flex-direction: column;
        }
        .options label {
            margin: 5px 0;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
        }
        .options label:hover {
            background-color: #f0f0f0;
            transform: scale(1.02);
        }
        .options input[type="radio"] {
            margin-right: 10px;
        }
        .results {
            display: none;
            margin-top: 20px;
            padding: 20px;
            background-color: #e8f5e9;
            border-radius: 5px;
        }
        .results h2 {
            color: #2e7d32;
        }
        .results p {
            font-size: 1.1em;
        }
        button {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #6200ea;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #3700b3;
        }
    </style>
</head>
<body>
    <div class="quiz-container">
        <h1>Quiz de Personnalité</h1>
        <div class="question">
            <h2>1. Lorsqu'on vous donne une tâche importante, quelle est votre réaction ?</h2>
            <div class="options">
                <label><input type="radio" name="q1" value="A"> A) Je veux qu’elle soit parfaite, même si cela prend du temps.</label>
                <label><input type="radio" name="q1" value="B"> B) J’essaie de satisfaire tout le monde en la faisant bien.</label>
                <label><input type="radio" name="q1" value="C"> C) Je me concentre sur le succès et le résultat final.</label>
                <label><input type="radio" name="q1" value="D"> D) Je cherche à y mettre ma touche personnelle pour la rendre unique.</label>
                <label><input type="radio" name="q1" value="E"> E) J’analyse tous les détails avant de commencer.</label>
                <label><input type="radio" name="q1" value="F"> F) Je veux être sûr(e) que tout se passera sans risque.</label>
                <label><input type="radio" name="q1" value="G"> G) Je cherche une façon amusante et originale de la faire.</label>
                <label><input type="radio" name="q1" value="H"> H) Je prends rapidement les commandes pour organiser tout le monde.</label>
                <label><input type="radio" name="q1" value="I"> I) Je fais en sorte que tout le monde s’entende bien dans l’équipe.</label>
            </div>
        </div>
        <div class="question">
            <h2>2. Quelle phrase vous correspond le plus ?</h2>
            <div class="options">
                <label><input type="radio" name="q2" value="A"> A) « Je veux faire les choses parfaitement. »</label>
                <label><input type="radio" name="q2" value="B"> B) « J’aime aider les autres et être apprécié(e). »</label>
                <label><input type="radio" name="q2" value="C"> C) « Je veux réussir et être reconnu(e) pour mes talents. »</label>
                <label><input type="radio" name="q2" value="D"> D) « Je me sens différent(e) et spécial(e). »</label>
                <label><input type="radio" name="q2" value="E"> E) « J’ai besoin de comprendre avant d’agir. »</label>
                <label><input type="radio" name="q2" value="F"> F) « Je cherche avant tout la sécurité et la stabilité. »</label>
                <label><input type="radio" name="q2" value="G"> G) « Je veux profiter de la vie et éviter les contraintes. »</label>
                <label><input type="radio" name="q2" value="H"> H) « J’aime diriger et prendre des décisions. »</label>
                <label><input type="radio" name="q2" value="I"> I) « J’aime maintenir l’équilibre et éviter les conflits. »</label>
            </div>
        </div>
        <div class="question">
            <h2>3. Dans un groupe, quel rôle prenez-vous naturellement ?</h2>
            <div class="options">
                <label><input type="radio" name="q3" value="A"> A) Celui qui veille à ce que tout soit bien fait.</label>
                <label><input type="radio" name="q3" value="B"> B) Celui qui s’assure que tout le monde va bien.</label>
                <label><input type="radio" name="q3" value="C"> C) Celui qui motive et pousse les autres à réussir.</label>
                <label><input type="radio" name="q3" value="D"> D) Celui qui exprime ses émotions et ses idées créatives.</label>
                <label><input type="radio" name="q3" value="E"> E) Celui qui observe et analyse la situation avant d’agir.</label>
                <label><input type="radio" name="q3" value="F"> F) Celui qui cherche à créer un environnement stable.</label>
                <label><input type="radio" name="q3" value="G"> G) Celui qui apporte de la joie et des idées nouvelles.</label>
                <label><input type="radio" name="q3" value="H"> H) Celui qui prend les devants et dirige.</label>
                <label><input type="radio" name="q3" value="I"> I) Celui qui apaise les tensions et favorise l’harmonie.</label>
            </div>
        </div>
        <div class="question">
            <h2>4. Face à un problème, comment réagissez-vous ?</h2>
            <div class="options">
                <label><input type="radio" name="q4" value="A"> A) Je veux trouver la meilleure solution sans erreur.</label>
                <label><input type="radio" name="q4" value="B"> B) Je demande l’avis des autres et les soutiens.</label>
                <label><input type="radio" name="q4" value="C"> C) Je cherche le moyen le plus rapide et efficace pour gagner.</label>
                <label><input type="radio" name="q4" value="D"> D) Je me base sur mes sentiments et ma créativité.</label>
                <label><input type="radio" name="q4" value="E"> E) J’étudie toutes les possibilités avant de me décider.</label>
                <label><input type="radio" name="q4" value="F"> F) J’évite de prendre des risques inutiles.</label>
                <label><input type="radio" name="q4" value="G"> G) Je cherche une issue plaisante et évite la négativité.</label>
                <label><input type="radio" name="q4" value="H"> H) Je prends le contrôle et impose une solution.</label>
                <label><input type="radio" name="q4" value="I"> I) Je cherche à éviter les conflits et à calmer la situation.</label>
            </div>
        </div>
        <button onclick="showResults()">Voir les résultats</button>
        <div class="results" id="results">
            <h2>🌟 Résultats : Découvrez votre personnalité dominante !</h2>
            <p id="result-text"></p>
        </div>
    </div>
    <script>
        function showResults() {
            const answers = {
                A: 0, B: 0, C: 0, D: 0, E: 0, 
                F: 0, G: 0, H: 0, I: 0
            };

            let isAnswered = false;

            // Compter les réponses
            const inputs = document.querySelectorAll('input[type="radio"]:checked');
            if (inputs.length < 4) {
                alert("Veuillez répondre à toutes les questions avant de voir les résultats !");
                return;
            }

            inputs.forEach(input => {
                const value = input.value;
                if (answers.hasOwnProperty(value)) {
                    answers[value]++;
                    isAnswered = true;
                }
            });

            let maxKey = 'A';
            let maxValue = answers['A'];

            for (const key in answers) {
                if (answers[key] > maxValue) {
                    maxKey = key;
                    maxValue = answers[key];
                }
            }

            const resultText = document.getElementById('result-text');
            const results = {
                A: 'Le Perfectionniste : Vous aimez que tout soit bien fait et vous vous imposez des standards élevés.',
                B: 'L\'Altruiste : Vous êtes une personne bienveillante qui aime aider et être apprécié(e).',
                C: 'Le Battant : Vous êtes motivé(e) par la réussite et aimez relever des défis.',
                D: 'Le Romantique : Vous ressentez un besoin d’authenticité et d’unicité.',
                E: 'L\'Observateur : Vous êtes curieux(se) et aimez l’analyse et la réflexion.',
                F: 'Le Loyaliste : Vous recherchez la sécurité et la stabilité.',
                G: 'L\'Épicurien : Vous aimez la liberté et profitez pleinement de la vie.',
                H: 'Le Leader : Vous aimez prendre des décisions et diriger les autres.',
                I: 'Le Médiateur : Vous cherchez l’harmonie et évitez les conflits.'
            };

            resultText.textContent = results[maxKey];
            document.getElementById('results').style.display = 'block';
        }
    </script>
</body>
</html>
