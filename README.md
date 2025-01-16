<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Projet Vacances Février</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f8ff;
        }
        header {
            background-color: #4682b4;
            color: white;
            text-align: center;
            padding: 1rem 0;
        }
        .container {
            max-width: 600px;
            margin: 2rem auto;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 2rem;
        }
        .section {
            margin-bottom: 1.5rem;
        }
        .section label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }
        .section select, .section input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .button {
            display: block;
            width: 100%;
            background-color: #4682b4;
            color: white;
            border: none;
            padding: 0.75rem;
            text-align: center;
            cursor: pointer;
            border-radius: 4px;
            font-size: 1rem;
        }
        .button:hover {
            background-color: #5a9bd6;
        }
        .result {
            margin-top: 1rem;
            font-size: 1.2rem;
            font-weight: bold;
            text-align: center;
            color: #333;
        }
    </style>
</head>
<body>
    <header>
        <h1>Projet Vacances Février</h1>
    </header>
    <div class="container">
        <div class="section">
            <label for="conversion-type">Que souhaitez-vous convertir ?</label>
            <select id="conversion-type">
                <option value="mass">Masse</option>
                <option value="volume">Volume</option>
            </select>
        </div>

        <div class="section">
            <label for="input-value">Valeur à convertir</label>
            <input type="number" id="input-value" placeholder="Entrez une valeur">
        </div>

        <div class="section">
            <label for="input-unit">Unité d'entrée</label>
            <select id="input-unit">
                <!-- Options seront générées dynamiquement -->
            </select>
        </div>

        <div class="section">
            <label for="output-unit">Unité de conversion</label>
            <select id="output-unit">
                <!-- Options seront générées dynamiquement -->
            </select>
        </div>

        <button class="button" onclick="convert()">Convertir</button>

        <div id="result" class="result"></div>
    </div>

    <script>
        const massUnits = ["t", "q", "kg", "hg", "dag", "g", "dg", "cg", "mg"];
        const volumeUnits = ["kL", "hL", "daL", "L", "dL", "cL", "mL"];

        const conversionType = document.getElementById('conversion-type');
        const inputUnit = document.getElementById('input-unit');
        const outputUnit = document.getElementById('output-unit');

        // Met à jour les options en fonction du type de conversion
        function updateUnits() {
            const units = conversionType.value === 'mass' ? massUnits : volumeUnits;
            inputUnit.innerHTML = outputUnit.innerHTML = units.map(unit => `<option value="${unit}">${unit}</option>`).join('');
        }

        // Conversion des unités
        function convert() {
            const value = parseFloat(document.getElementById('input-value').value);
            const fromUnit = inputUnit.value;
            const toUnit = outputUnit.value;

            if (isNaN(value)) {
                document.getElementById('result').innerText = 'Veuillez entrer une valeur valide.';
                return;
            }

            const unitFactors = {
                t: 1e6, q: 1e5, kg: 1e3, hg: 1e2, dag: 10, g: 1, dg: 0.1, cg: 0.01, mg: 0.001,
                kL: 1e3, hL: 1e2, daL: 10, L: 1, dL: 0.1, cL: 0.01, mL: 0.001
            };

            const result = value * unitFactors[fromUnit] / unitFactors[toUnit];
            document.getElementById('result').innerText = `Résultat : ${result.toFixed(2)} ${toUnit}`;
        }

        // Initialisation
        conversionType.addEventListener('change', updateUnits);
        updateUnits();
    </script>
</body>
</html>
