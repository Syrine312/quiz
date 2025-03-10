<html>
  <head>
    <title>Quiz : Quelle est votre personnalité émergente ?</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background: #f9f9f9;
        margin: 0;
        padding: 20px;
      }
      .quiz-container {
        max-width: 600px;
        margin: 0 auto;
        background: #fff;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      }
      h1 {
        text-align: center;
      }
      .question {
        margin-bottom: 20px;
      }
      .question h3 {
        margin-bottom: 10px;
      }
      .options label {
        display: block;
        margin-bottom: 5px;
      }
      button {
        display: block;
        margin: 20px auto;
        padding: 10px 20px;
        background: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
      }
      button:hover {
        background: #0056b3;
      }
      .result {
        margin-top: 20px;
        font-size: 1.2em;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <div class="quiz-container">
      <h1>Quiz : Quelle est votre personnalité émergente ?</h1>
      <form id="quizForm">
        <!-- Question 1 -->
        <div class="question">
          <h3>1. Comment réagissez-vous face à un défi inattendu ?</h3>
          <div class="options">
            <label
              ><input type="radio" name="q1" value="a" /> Je prends du recul et
              j'analyse la situation avant d'agir.</label
            >
            <label
              ><input type="radio" name="q1" value="b" /> J'agis immédiatement
              avec confiance, je trouverai une solution en chemin.</label
            >
            <label
              ><input type="radio" name="q1" value="c" /> Je demande conseil aux
              autres avant de prendre une décision.</label
            >
            <label
              ><input type="radio" name="q1" value="d" /> J'hésite beaucoup et
              j'ai du mal à me lancer.</label
            >
          </div>
        </div>
        <!-- Question 2 -->
        <div class="question">
          <h3>2. Quel mot décrit le mieux votre attitude face à l'avenir ?</h3>
          <div class="options">
            <label><input type="radio" name="q2" value="a" /> Ambition</label>
            <label
              ><input type="radio" name="q2" value="b" /> Spontanéité</label
            >
            <label><input type="radio" name="q2" value="c" /> Harmonie</label>
            <label><input type="radio" name="q2" value="d" /> Prudence</label>
          </div>
        </div>
        <!-- Question 3 -->
        <div class="question">
          <h3>
            3. Quand vous travaillez en groupe, quel rôle préférez-vous jouer ?
          </h3>
          <div class="options">
            <label
              ><input type="radio" name="q3" value="a" /> Leader, j’aime
              organiser et motiver l’équipe.</label
            >
            <label
              ><input type="radio" name="q3" value="b" /> Innovateur, j’apporte
              des idées originales et créatives.</label
            >
            <label
              ><input type="radio" name="q3" value="c" /> Médiateur, je veille à
              ce que tout le monde s’entende bien.</label
            >
            <label
              ><input type="radio" name="q3" value="d" /> Observateur, je
              préfère analyser avant d’intervenir.</label
            >
          </div>
        </div>
        <!-- Question 4 -->
        <div class="question">
          <h3>4. Comment gérez-vous vos émotions en période de stress ?</h3>
          <div class="options">
            <label
              ><input type="radio" name="q4" value="a" /> Je transforme mon
              stress en motivation pour réussir.</label
            >
            <label
              ><input type="radio" name="q4" value="b" /> Je garde une attitude
              positive et je vais de l’avant.</label
            >
            <label
              ><input type="radio" name="q4" value="c" /> Je cherche du soutien
              auprès de mes proches.</label
            >
            <label
              ><input type="radio" name="q4" value="d" /> J’ai tendance à me
              replier sur moi-même.</label
            >
          </div>
        </div>
        <!-- Question 5 -->
        <div class="question">
          <h3>5. Quelle est votre principale source de motivation ?</h3>
          <div class="options">
            <label
              ><input type="radio" name="q5" value="a" /> Atteindre mes
              objectifs et réussir.</label
            >
            <label
              ><input type="radio" name="q5" value="b" /> Explorer de nouvelles
              expériences et prendre des risques.</label
            >
            <label
              ><input type="radio" name="q5" value="c" /> Apporter du bien-être
              aux autres et vivre en harmonie.</label
            >
            <label
              ><input type="radio" name="q5" value="d" /> Assurer ma stabilité
              et éviter les erreurs.</label
            >
          </div>
        </div>
        <button type="button" onclick="calculateResult()">
          Voir le résultat
        </button>
      </form>
      <div class="result" id="result"></div>
    </div>

    <script>
      function calculateResult() {
        const form = document.getElementById("quizForm");
        const resultDiv = document.getElementById("result");

        // Comptage des réponses
        let counts = { a: 0, b: 0, c: 0, d: 0 };

        // Vérification que toutes les questions ont une réponse
        for (let i = 1; i <= 5; i++) {
          const radios = form.elements["q" + i];
          let answered = false;
          for (let radio of radios) {
            if (radio.checked) {
              counts[radio.value]++;
              answered = true;
              break;
            }
          }
          if (!answered) {
            resultDiv.innerHTML =
              "<p style='color:red;'>Veuillez répondre à toutes les questions.</p>";
            return;
          }
        }

        // Détermination de la réponse la plus fréquente
        let maxCount = 0;
        let personality = "";
        for (let key in counts) {
          if (counts[key] > maxCount) {
            maxCount = counts[key];
            personality = key;
          }
        }

        // Affichage du résultat
        let message = "";
        if (personality === "a") {
          message =
            "<h2>Le Leader Ambitieux</h2><p>Vous êtes une personne déterminée et persévérante. Vous aimez prendre des initiatives et guider les autres vers le succès.</p>";
        } else if (personality === "b") {
          message =
            "<h2>L’Explorateur Audacieux</h2><p>Vous êtes spontané et créatif. Vous aimez découvrir de nouvelles choses et sortir de votre zone de confort.</p>";
        } else if (personality === "c") {
          message =
            "<h2>L’Harmonisateur Bienveillant</h2><p>Vous êtes une personne empathique et à l’écoute. Vous privilégiez l’équilibre et les relations humaines.</p>";
        } else if (personality === "d") {
          message =
            "<h2>L’Observateur Prudent</h2><p>Vous êtes réfléchi et méthodique. Vous aimez analyser avant d’agir et assurer la stabilité autour de vous.</p>";
        }

        resultDiv.innerHTML = message;
      }
    </script>
  </body>
</html>
