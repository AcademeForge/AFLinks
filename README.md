
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AcademeForge - Class Selection</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #121212;
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            text-align: center;
        }

        .container {
            width: 90%;
            max-width: 400px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            animation: fadeIn 0.5s ease-in-out;
        }

        h2 {
            margin-bottom: 15px;
            font-size: 22px;
        }

        .option {
            background: #1e1e1e;
            padding: 12px;
            margin: 10px 0;
            border-radius: 10px;
            cursor: pointer;
            font-size: 18px;
            transition: 0.3s;
            box-shadow: 0 4px 8px rgba(255, 255, 255, 0.1);
        }

        .option:hover {
            background: #292929;
            transform: scale(1.05);
        }

        .hidden {
            display: none;
        }

        .access-button {
            background: #00c853;
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            margin-top: 5px;
            transition: 0.3s;
        }

        .access-button:hover {
            background: #00e676;
            transform: scale(1.1);
        }

        .back-button {
            background: #ff5252;
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 14px;
            margin-top: 10px;
            transition: 0.3s;
        }

        .back-button:hover {
            background: #ff1744;
            transform: scale(1.1);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
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
<div class="container hidden" id="streamContainer">
    <h2>Select Your Stream</h2>
    <div class="option" onclick="selectStream('Science')">Science</div>
    <div class="option" onclick="selectStream('Commerce')">Commerce</div>
    <div class="option" onclick="selectStream('Arts')">Arts</div>
    <button class="back-button" onclick="goBack('streamContainer', 'classContainer')">Back</button>
</div>

<!-- Subject Selection -->
<div class="container hidden" id="subjectContainer">
    <h2>Subjects</h2>
    <div id="subjectsList"></div>
    <button class="back-button" onclick="goBack('subjectContainer', selectedClass > 10 ? 'streamContainer' : 'classContainer')">Back</button>
</div>

<script>
    let selectedClass = null;
    let selectedStream = null;

    const subjectLinks = {
        1: { "Math": "#", "English": "#", "Hindi": "#" },
        2: { "Math": "#", "English": "#", "Hindi": "#" },
        3: { "Math": "#", "English": "#", "Hindi": "#" },
        4: { "Math": "#", "English": "#", "Hindi": "#" },
        5: { "Math": "#", "English": "#", "Hindi": "#" },
        6: { "Science": "#", "Math": "#", "English": "#", "Hindi": "#" },
        7: { "Science": "#", "Math": "#", "English": "#", "Hindi": "#" },
        8: { "Science": "#", "Math": "#", "Social Science": "#", "English": "#", "Hindi": "#" },
        9: { "Science": "#", "Math": "#", "Social Science": "#", "English": "#", "Hindi": "#" },
        10: { "Science": "#", "Math": "#", "Social Science": "#", "English": "#", "Hindi": "#" },
        11: {
            "Science": { "Physics": "#", "Chemistry": "#", "Math": "#", "Biology": "#" },
            "Commerce": { "Business Studies": "#", "Accountancy": "#", "Economics": "#" },
            "Arts": { "History": "#", "Political Science": "#", "Geography": "#", "Psychology": "#" }
        },
        12: {
            "Science": { "Physics": "#", "Chemistry": "#", "Math": "#", "Biology": "#" },
            "Commerce": { "Business Studies": "#", "Accountancy": "#", "Economics": "#" },
            "Arts": { "History": "#", "Political Science": "#", "Geography": "#", "Psychology": "#" }
        }
    };

    function selectClass(cls) {
        selectedClass = cls;
        document.getElementById("classContainer").classList.add("hidden");
        if (cls > 10) {
            document.getElementById("streamContainer").classList.remove("hidden");
        } else {
            loadSubjects(cls);
        }
    }

    function selectStream(stream) {
        selectedStream = stream;
        document.getElementById("streamContainer").classList.add("hidden");
        loadSubjects(selectedClass);
    }

    function loadSubjects(cls) {
        const subjectsList = document.getElementById("subjectsList");
        subjectsList.innerHTML = '';

        let subjects = cls <= 10 ? subjectLinks[cls] : subjectLinks[cls][selectedStream];

        for (const [subject, link] of Object.entries(subjects)) {
            subjectsList.innerHTML += `
                <div class="option">
                    ${subject}
                    <button class="access-button" onclick="window.open('${link}', '_blank')">Access Notes</button>
                </div>
            `;
        }

        document.getElementById("subjectContainer").classList.remove("hidden");
    }

    function goBack(current, previous) {
        document.getElementById(current).classList.add("hidden");
        document.getElementById(previous).classList.remove("hidden");
    }
</script>

</body>
</html>