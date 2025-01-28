<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dissertation Creator</title>
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
    <textarea id="theme" placeholder="Enter a theme for your dissertation..."></textarea>
    <button id="generate">Generate Dissertation</button>
    <div id="output" style="margin-top: 20px; width: 80%; font-size: 16px;"></div>

    <script>
        document.getElementById('generate').addEventListener('click', function() {
            const theme = document.getElementById('theme').value;
            const output = document.getElementById('output');

            if (theme.trim() === '') {
                output.innerHTML = '<p style="color: red;">Please enter a theme.</p>';
                return;
            }

            const dissertation = `Here is a dissertation based on the theme: "${theme}". \n\n` +
                `Introduction:\n\nThe theme of "${theme}" has long been a subject of interest across various disciplines. ` +
                `This dissertation explores its significance, implications, and potential impacts.` +
                `\n\nMain Body:\n\nFirst, we delve into the historical context and relevance of "${theme}". ` +
                `This is followed by an analysis of its current significance in modern society. Finally, potential future developments are considered.` +
                `\n\nConclusion:\n\nIn conclusion, the exploration of "${theme}" provides valuable insights into its broader implications, ` +
                `emphasizing the need for ongoing study and engagement.`;

            output.textContent = dissertation;
        });
    </script>
</body>
</html>
