<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crying Cat App</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        #crying-cat {
            display: none;
            max-width: 100%;
            max-height: 80%;
        }
    </style>
</head>
<body>
    <img id="crying-cat" src="https://i.imgur.com/jLRA3R8.png" alt="Crying Cat">

    <script>
        document.addEventListener('keydown', function(event) {
            if (event.code === 'Space') {
                const catImage = document.getElementById('crying-cat');
                catImage.style.display = 'block';
            }
        });
    </script>
</body>
</html>
