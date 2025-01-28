<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Créateur de Dissertation</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        textarea {
            width: 80%;
            height: 200px;
            margin-bottom: 20px;
            font-size: 16px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 8px;
            resize: none;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <textarea id="theme" placeholder="Entrez un thème pour votre dissertation..."></textarea>
    <button id="generate">Générer la Dissertation</button>
    <div id="output" style="margin-top: 20px; width: 80%; font-size: 16px;"></div>

    <script>
        document.getElementById('generate').addEventListener('click', function() {
            const theme = document.getElementById('theme').value;
            const output = document.getElementById('output');

            if (theme.trim() === '') {
                output.innerHTML = '<p style="color: red;">Veuillez entrer un thème.</p>';
                return;
            }

            const dissertation = `Voici une dissertation basée sur le thème : "${theme}". \n\n` +
                `Introduction :\n\nLe thème de "${theme}" a longtemps été un sujet d'intérêt dans divers domaines. ` +
                `Cette dissertation explore son importance, ses implications et ses impacts potentiels.` +
                `\n\nDéveloppement :\n\nTout d'abord, nous examinerons le contexte historique et la pertinence de "${theme}". ` +
                `Ensuite, une analyse de son importance actuelle dans la société moderne sera proposée. Enfin, les développements futurs potentiels seront envisagés.` +
                `\n\nConclusion :\n\nEn conclusion, l'exploration de "${theme}" offre des perspectives précieuses sur ses implications plus larges, ` +
                `soulignant la nécessité de continuer à l'étudier et à s'y intéresser.`;

            output.textContent = dissertation;
        });
    </script>
</body>
</html>
