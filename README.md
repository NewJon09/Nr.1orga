<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bunte Organizer-Website</title>
    <style>
        body {
            background-color: #f4f4f4;
            color: #333;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
        }

        header {
            text-align: center;
            padding: 20px;
            background-color: #4285f4;
            color: #fff;
        }

        section {
            padding: 20px;
            box-shadow: 0 0 10px rgba(43, 41, 41, 0.1);
            margin: 20px;
            background-color: #ffffff;
            border-radius: 8px;
        }

        h1 {
            color: #656e7d;
            text-shadow: 2px 2px 4px #ccc;
        }

        p {
            font-size: 18px;
            line-height: 1.6;
            margin-bottom: 10px;
        }

        ul {
            list-style-type: square;
            margin-left: 20px;
        }

        input {
            width: 80%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            padding: 10px;
            background-color: #34a853;
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 4px;
        }

        button:hover {
            background-color: #2d8a5f;
        }

        #timerSection {
            display: none;
        }

        #timerInput {
            width: 60px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
    </style>
</head>
<body>

    <header>
        <h1>Die Nr1. Organizer-Website</h1>
    </header>

    <section id="notizenSection">
        <h2>Notizen</h2>
        <ul id="notizenList">
            <!-- Hier werden Notizen dynamisch hinzugefügt -->
        </ul>
        <input type="text" id="notizInput" placeholder="Neue Notiz eingeben">
        <button onclick="addNotiz()">Notiz hinzufügen</button>
    </section>

    <section id="timerSection">
        <h2>Timer</h2>
        <p>Setze einen Timer (in Sekunden):</p>
        <input type="number" id="timerInput" min="1" value="1">
        <button onclick="startTimer()">Start</button>
        <p id="timerOutput"></p>
    </section>

    <section id="einkaufslisteSection">
        <h2>Einkaufsliste</h2>
        <ul id="einkaufsliste">
            <!-- Hier werden Einkaufsliste-Elemente dynamisch hinzugefügt -->
        </ul>
        <input type="text" id="einkaufslisteInput" placeholder="Neues Element hinzufügen">
        <button onclick="addElement()">Element hinzufügen</button>
    </section>

    <script>
        function addNotiz() {
            var notizInput = document.getElementById('notizInput');
            var notizenList = document.getElementById('notizenList');
            var notizText = notizInput.value.trim();

            if (notizText !== '') {
                var li = document.createElement('li');
                li.textContent = notizText;
                notizenList.appendChild(li);
                notizInput.value = '';
            }
        }

        function startTimer() {
            var timerInput = document.getElementById('timerInput');
            var timerOutput = document.getElementById('timerOutput');
            var seconds = parseInt(timerInput.value);

            if (!isNaN(seconds) && seconds > 0) {
                timerOutput.textContent = 'Timer läuft...';

                setTimeout(function () {
                    timerOutput.textContent = 'Timer abgelaufen!';
                }, seconds * 1000);
            }
        }

        function addElement() {
            var einkaufslisteInput = document.getElementById('einkaufslisteInput');
            var einkaufsliste = document.getElementById('einkaufsliste');
            var elementText = einkaufslisteInput.value.trim();

            if (elementText !== '') {
                var li = document.createElement('li');
                li.textContent = elementText;
                einkaufsliste.appendChild(li);
                einkaufslisteInput.value = '';
            }
        }
    </script>

</body>
</html>
