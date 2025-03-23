<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>AcademeForge - Mobile Portal</title>
    <style>
        /* Root Variables for Colors & Effects */
        :root {
            --bg-gradient: linear-gradient(135deg, #007bff, #6610f2);
            --card-bg: rgba(255, 255, 255, 0.9);
            --button-color: #ff5722;
            --button-hover: #e64a19;
            --text-color: #fff;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            --transition: 0.3s;
        }

        /* General Styles */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background: var(--bg-gradient);
            color: var(--text-color);
            text-align: center;
            overflow: hidden;
        }

        .container {
            width: 90%;
            max-width: 400px;
            background: var(--card-bg);
            padding: 20px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            transform: scale(0.9);
            opacity: 0;
            animation: fadeIn 0.5s forwards;
        }

        h2 {
            font-size: 1.5em;
            margin-bottom: 15px;
            color: #333;
        }

        .option {
            background: var(--button-color);
            color: white;
            padding: 12px;
            margin: 10px 0;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.1em;
            transition: var(--transition);
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .option::after {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transform: scale(0);
            transition: var(--transition);
            border-radius: 50%;
        }

        .option:hover::after {
            transform: scale(3);
        }

        .option:hover {
            background: var(--button-hover);
            transform: scale(1.05);
        }

        .access-button {
            background: #28a745;
            color: white;
            padding: 8px 12px;
            border-radius: 5px;
            font-size: 0.9em;
            margin-top: 5px;
            display: block;
            text-decoration: none;
            transition: var(--transition);
        }

        .access-button:hover {
            background: #218838;
        }

        #backButton {
            background: #333;
            color: white;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            cursor: pointer;
            display: none;
            font-size: 0.9em;
            transition: var(--transition);
        }

        #backButton:hover {
            background: #444;
        }

        /* Animation */
        @keyframes fadeIn {
            to {
                transform: scale(1);
                opacity: 1;
            }
        }

        /* Mobile-Only Optimization */
        @media (min-width: 768px) {
            body {
                display: none;
            }
        }
    </style>
</head>
<body>

    <!-- Class Selection -->
    <div class="container" id="classContainer">
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

    <!-- Stream Selection -->
    <div class="container" id="streamContainer" style="display: none;">
        <h2>Select Your Stream</h2>
        <div class="option" onclick="selectStream('Science')">Science</div>
        <div class="option" onclick="selectStream('Commerce')">Commerce</div>
        <div class="option" onclick="selectStream('Arts')">Arts</div>
    </div>

    <!-- Subjects -->
    <div class="container" id="subjectContainer" style="display: none;">
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
            document.getElementById(`${currentPage}Container`).style.display = 'none';
            document.getElementById(`${page}Container`).style.display = 'block';
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
                        <a href="#" class="access-button">Access to Notes</a>
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