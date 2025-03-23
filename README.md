
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>AcademeForge - Select Class</title>
    <style>
        /* Root Variables */
        :root {
            --bg-color: #f8f9fa;
            --text-color: #333;
            --card-bg: #fff;
            --primary-color: #007bff;
            --hover-color: #0056b3;
            --transition: 0.3s;
        }

        /* General Styles */
        body {
            font-family: 'Arial', sans-serif;
            background: var(--bg-color);
            color: var(--text-color);
            text-align: center;
            margin: 0;
            padding: 10px;
            transition: var(--transition);
        }

        .container {
            display: none;
            width: 95%;
            max-width: 400px;
            margin: auto;
            padding: 15px;
            background: var(--card-bg);
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
        }

        h2 {
            font-size: 1.4em;
            margin-bottom: 15px;
        }

        .option {
            background: var(--primary-color);
            color: white;
            padding: 12px;
            margin: 8px 0;
            border-radius: 5px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1.1em;
        }

        .option:hover {
            background: var(--hover-color);
        }

        .access-button {
            background: var(--hover-color);
            color: white;
            padding: 8px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
            margin-top: 5px;
            font-size: 0.9em;
        }

        .access-button:hover {
            background: var(--primary-color);
        }

        #backButton {
            background: var(--primary-color);
            color: white;
            padding: 10px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            display: none;
            font-size: 0.9em;
        }

        #backButton:hover {
            background: var(--hover-color);
        }

        /* Show Active Page */
        .show {
            display: block;
        }

        /* Mobile-Only Optimization */
        @media (min-width: 768px) {
            body {
                display: none; /* Hide on non-mobile devices */
            }
        }
    </style>
</head>
<body>

    <!-- Class Selection Page -->
    <div class="container show" id="classContainer">
        <h2>Select Your Class</h2>
        <div class="option" onclick="selectClass(1)">Class 1</div>
        <div class="option" onclick="selectClass(2)">Class 2</div>
        <div class="option" onclick="selectClass(3)">Class 3</div>
        <div class="option" onclick="selectClass(4)">Class 4</div>
        <div class="option" onclick="selectClass(5)">Class 5</div>
        <div class="option" onclick="selectClass(6)">Class 6</div>
        <div class="option" onclick="selectClass(7)">Class 7</div>
        <div class="option" onclick="selectClass(8)">Class 8</div>
        <div class="option" onclick="selectClass(9)">Class 9</div>
        <div class="option" onclick="selectClass(10)">Class 10</div>
        <div class="option" onclick="selectClass(11)">Class 11</div>
        <div class="option" onclick="selectClass(12)">Class 12</div>
    </div>

    <!-- Stream Selection Page -->
    <div class="container" id="streamContainer">
        <h2>Select Your Stream</h2>
        <div class="option" onclick="selectStream('Science')">Science</div>
        <div class="option" onclick="selectStream('Commerce')">Commerce</div>
        <div class="option" onclick="selectStream('Arts')">Arts</div>
    </div>

    <!-- Subjects Page -->
    <div class="container" id="subjectContainer">
        <h2>Subjects</h2>
        <div id="subjectsList"></div>
    </div>

    <!-- Back Button -->
    <button id="backButton" onclick="goBack()">🔙 Back</button>

    <script>
        let currentPage = 'class';
        let selectedClass = null;
        let selectedStream = null;

        function showPage(page) {
            document.getElementById(`${currentPage}Container`).classList.remove('show');
            document.getElementById(`${page}Container`).classList.add('show');
            document.getElementById('backButton').style.display = (page !== 'class') ? 'block' : 'none';
            currentPage = page;
        }

        function selectClass(cls) {
            selectedClass = cls;
            if (cls >= 11) {
                showPage('stream');
            } else {
                loadSubjects();
            }
        }

        function selectStream(stream) {
            selectedStream = stream;
            loadSubjects();
        }

        function loadSubjects() {
            const subjectsList = document.getElementById('subjectsList');
            subjectsList.innerHTML = '';

            let subjects = [];
            if (selectedClass <= 10) {
                subjects = ["Math", "Science", "Social Science", "English", "Hindi"];
            } else if (selectedStream === "Science") {
                subjects = ["Physics", "Chemistry", "Math", "Biology"];
            } else if (selectedStream === "Commerce") {
                subjects = ["Business Studies", "Accountancy", "Economics"];
            } else if (selectedStream === "Arts") {
                subjects = ["History", "Political Science", "Economics", "Psychology", "Geography"];
            }

            subjects.forEach(subject => {
                subjectsList.innerHTML += `
                    <div class="option">
                        ${subject}
                        <button class="access-button">Access to Notes</button>
                    </div>
                `;
            });

            showPage('subject');
        }

        function goBack() {
            if (currentPage === 'subject') showPage(selectedClass > 10 ? 'stream' : 'class');
            else if (currentPage === 'stream') showPage('class');
        }
    </script>

</body>
</html>