# bevardis18.github.io
<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nusikaltimų pasekmės ir Baudos</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            background-color: #000000;
            color: #FFFFFF;
        }

        .section-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 10px;
        }

        .section-title {
            font-size: 20px;
            font-weight: bold;
            margin: 10px 0;
            color: #FFFFFF;
        }

        .button-section {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }

        .button, .double-ket-button {
            background-color: #007BFF;
            border: none;
            color: white;
            padding: 10px 15px;
            border-radius: 5px;
            font-size: 14px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .button.selected, .double-ket-button.selected {
            background-color: #28a745;
        }

        .total, .total-second {
            font-size: 24px;
            font-weight: bold;
            margin: 10px 0;
            color: #FFFFFF;
        }
    </style>
</head>
<body>

    <h1>Nusikaltimų pasekmės ir Baudos</h1>

    <!-- Button to double KET fines and jail times -->
    <button class="double-ket-button" onclick="doubleKETPenalties()">Padvigubinti KET pažeidimų baudas</button>

    <!-- Total fines and jail time display -->
    <div class="total" id="totalSum">Baudos: 0</div>
    <div class="total-second" id="totalAdditionalSum">Kalejimo laikas: 0</div>

    <!-- Crime Sections -->
    <div class="section-container">
        <div class="section-title">Nusikalstama veikla</div>
        <div class="button-section">
            <button class="button" onclick="toggleButton(5000, 35, 'Buvimas neleistinoje lokacijoje', 'ket')">Buvimas neleistinoje lokacijoje</button>
            <button class="button" onclick="toggleButton(5000, 35, 'Trp. vagystė', 'ket')">Trp. vagystė</button>
            <button class="button" onclick="toggleButton(3000, 45, 'Ginkluotas pasikėsinimas į gyvybę', 'ket')">Ginkluotas pasikėsinimas į gyvybę</button>
            <button class="button" onclick="toggleButton(5000, 45, 'Daugkartinis namų plėšimas', 'ket')">Daugkartinis namų plėšimas</button>
            <button class="button" onclick="toggleButton(2000, 15, 'Svetimo turto išviliojimas', 'ket')">Svetimo turto išviliojimas</button>
            <button class="button" onclick="toggleButton(5000, 45, 'Pasikesinimas i pareiguno/ų gyvybę/es', 'ket')">Pasikesinimas i pareiguno/ų gyvybę/es</button>
            <button class="button" onclick="toggleButton(2500, 10, 'Neteisėtų pinigų laikymas (nuo 3k iki 20k)', 'ket')">Neteisėtų pinigų laikymas (nuo 3k iki 20k)</button>
            <button class="button" onclick="toggleButton(7500, 20, 'Neteisėtų pinigų laikymas (nuo 20k)', 'ket')">Neteisėtų pinigų laikymas (nuo 20k)</button>
            <button class="button" onclick="toggleButton(5000, 45, 'Neteisėto ginklo laikymas', 'ket')">Neteisėto ginklo laikymas</button>
            <button class="button" onclick="toggleButton(7500, 25, 'Narkotinių medžiagų turėjimas (siekiant parduoti)', 'ket')">Narkotinių medžiagų turėjimas (siekiant parduoti)</button>
            <button class="button" onclick="toggleButton(2000, 15, 'bendradarbiavimas nusikalstamoje veikloje', 'ket')">bendradarbiavimas nusikalstamoje veikloje</button>
            <button class="button" onclick="toggleButton(4500, 45, 'Banko plėšimas', 'ket')">Banko plėšimas</button>
            <button class="button" onclick="toggleButton(5000, 30, 'Brakonieriavimas', 'ket')">Brakonieriavimas</button>
            <button class="button" onclick="toggleButton(2500, 45, 'Asmens pagrobimas', 'ket')">Asmens pagrobimas</button>
            <button class="button" onclick="toggleButton(4500, 60, 'Pareigūno/Mediko/Mechaniko užpuolimas/pasikesinimas i gyvybę', 'ket')">Pareigūno/Mediko/Mechaniko užpuolimas/pasikesinimas i gyvybę</button>
            <button class="button" onclick="toggleButton(5000, 75, 'Organizuotas nusikalstamumas', 'ket')">Organizuotas nusikalstamumas</button>
            <button class="button" onclick="toggleButton(4500, 55, 'Šarvuočio plėšimas', 'ket')">Šarvuočio plėšimas</button>
        </div>
    </div>

    <div class="section-container">
        <div class="section-title">Smurtiniai nusikaltimai</div>
        <div class="button-section">
            <button class="button" onclick="toggleButton(800, 5, 'Smulkių sužalojimų sukėlimas', 'non-ket')">Smulkių sužalojimų sukėlimas</button>
            <button class="button" onclick="toggleButton(2000, 10, 'Apiplėšimas', 'non-ket')">Apiplėšimas</button>
            <button class="button" onclick="toggleButton(4000, 30, 'Piktybiniai sužalojimai', 'non-ket')">Piktybiniai sužalojimai</button>
            <button class="button" onclick="toggleButton(6000, 45, 'Žmogžudystė', 'non-ket')">Žmogžudystė</button>
            <button class="button" onclick="toggleButton(2500, 15, 'Kankinimai', 'non-ket')">Kankinimai</button>
            <button class="button" onclick="toggleButton(2500, 30, 'Riaušių kurstymas', 'non-ket')">Riaušių kurstymas</button>
        </div>
    </div>

    <div class="section-container">
        <div class="section-title">KET pažeidimai</div>
        <div class="button-section">
            <button class="button" onclick="toggleButton(1000, 5, 'Greitis viršytas 10-20 km/h', 'ket')">Greitis viršytas 10-20 km/h</button>
            <button class="button" onclick="toggleButton(1500, 10, 'Greitis viršytas 20-30 km/h', 'ket')">Greitis viršytas 20-30 km/h</button>
            <button class="button" onclick="toggleButton(2500, 15, 'Greitis viršytas 30-40 km/h', 'ket')">Greitis viršytas 30-40 km/h</button>
            <button class="button" onclick="toggleButton(3500, 20, 'Greitis viršytas 40-50 km/h', 'ket')">Greitis viršytas 40-50 km/h</button>
            <button class="button" onclick="toggleButton(4500, 25, 'Greitis viršytas daugiau nei 50 km/h', 'ket')">Greitis viršytas daugiau nei 50 km/h</button>
            <button class="button" onclick="toggleButton(2000, 10, 'Parkavimas neleistinoje vietoje', 'ket')">Parkavimas neleistinoje vietoje</button>
            <button class="button" onclick="toggleButton(3000, 15, 'Kelio ženklų nesilaikymas', 'ket')">Kelio ženklų nesilaikymas</button>
            <button class="button" onclick="toggleButton(3000, 15, 'Važiavimas neblaiviam', 'ket')">Važiavimas neblaiviam</button>
            <button class="button" onclick="toggleButton(5000, 20, 'Eismo įvykis (sukeltas)', 'ket')">Eismo įvykis (sukeltas)</button>
        </div>
    </div>

    <div class="section-container">
        <div class="section-title">Viešos tvarkos pažeidimai</div>
        <div class="button-section">
            <button class="button" onclick="toggleButton(500, 5, 'Triukšmo kėlimas naktį', 'non-ket')">Triukšmo kėlimas naktį</button>
            <button class="button" onclick="toggleButton(1000, 10, 'Viešas neblaivumas', 'non-ket')">Viešas neblaivumas</button>
            <button class="button" onclick="toggleButton(1500, 15, 'Nevykdomas pareigūnų reikalavimas', 'non-ket')">Nevykdomas pareigūnų reikalavimas</button>
            <button class="button" onclick="toggleButton(2000, 20, 'Nesusiklausymas į viešąją tvarką', 'non-ket')">Nesusiklausymas į viešąją tvarką</button>
            <button class="button" onclick="toggleButton(2500, 25, 'Netinkamas elgesys viešose vietose', 'non-ket')">Netinkamas elgesys viešose vietose</button>
        </div>
    </div>

    <!-- JavaScript Functionality -->
    <script>
        let totalFine = 0;
        let totalJailTime = 0;
        let selectedButtons = {};

        function updateTotals() {
            totalFine = 0;
            totalJailTime = 0;
            for (const key in selectedButtons) {
                totalFine += selectedButtons[key].fine;
                totalJailTime += selectedButtons[key].jail;
            }
            document.getElementById("totalSum").innerText = `Baudos: ${totalFine}`;
            document.getElementById("totalAdditionalSum").innerText = `Kalejimo laikas: ${totalJailTime}`;
        }

        function toggleButton(fine, jail, description, type) {
            if (selectedButtons[description]) {
                delete selectedButtons[description];
            } else {
                selectedButtons[description] = { fine, jail, type };
            }
            updateTotals();
        }

        function doubleKETPenalties() {
            for (const key in selectedButtons) {
                if (selectedButtons[key].type === 'ket') {
                    selectedButtons[key].fine *= 2;
                    selectedButtons[key].jail *= 2;
                }
            }
            updateTotals();
        }
    </script>

</body>
</html>
