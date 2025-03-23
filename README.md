<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AcademeForge - Study Material</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f4f4f9;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        .container {
            max-width: 400px;
            background: white;
            padding: 20px;
            margin: 20px auto;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        h2 {
            color: #333;
        }
        .option {
            background: #007BFF;
            color: white;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
        }
        .option:hover {
            background: #0056b3;
        }
        .access-button {
            background: #28a745;
            color: white;
            border: none;
            padding: 8px 12px;
            margin-top: 5px;
            cursor: pointer;
            border-radius: 4px;
        }
        .access-button:hover {
            background: #218838;
        }
        .hidden {
            display: none;
        }
        #backButton {
            display: none;
            background: #dc3545;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            margin-bottom: 10px;
        }
        #backButton:hover {
            background: #c82333;
        }
    </style>
</head>
<body>

<!-- Back Button -->
<button id="backButton" onclick="goBack()">Back</button>

<!-- Class Selection Page -->
<div class="container" id="classContainer">
    <h2>Select Your Class</h2>
    <div class="option" onclick="selectClass(9)">Class 9</div>
    <div class="option" onclick="selectClass(10)">Class 10</div>
    <div class="option" onclick="selectClass(11)">Class 11</div>
    <div class="option" onclick="selectClass(12)">Class 12</div>
</div>

<!-- Stream Selection Page -->
<div class="container hidden" id="streamContainer">
    <h2>Select Your Stream</h2>
    <div class="option" onclick="selectStream('Science')">Science</div>
    <div class="option" onclick="selectStream('Commerce')">Commerce</div>
    <div class="option" onclick="selectStream('Arts')">Arts</div>
</div>

<!-- Subjects Page -->
<div class="container hidden" id="subjectContainer">
    <h2>Subjects</h2>
    <div id="subjectsList"></div>
</div>

<script>
    let currentPage = 'class';
    let selectedClass = null;
    let selectedStream = null;

    const subjectLinks = {
        9: {
            "Science": "https://drive.google.com/drive/folders/1-CtgsAx1kXo67-UUf6HsBunPIgm8FgUl",
            "Math": "https://drive.google.com/drive/folders/1-DH3yoNSnF0iFSIH2CsGGf5RobYwYKyp",
            "Social Science": "https://drive.google.com/drive/folders/1-Dm4Tg6UIlYBiNqGYOYAWZvJExikh7my",
            "English": "https://drive.google.com/drive/folders/1-Gd2i8_7ylzy-gM_sFQMGrtDbiE70vRr",
            "Hindi": "https://drive.google.com/drive/folders/1-EHtC6OQMkNE3qEU5JgPggm5I4ggUWf9"
        },
        10: {
            "Science": "https://drive.google.com/drive/folders/1-bVnCZbCabVmNGCxJ0gY4-FP4BwN9F02",
            "Math": "https://drive.google.com/drive/folders/1-Z7LCbOvKhHvMxqXS3W4qVcAukPVmhXK",
            "Social Science": "https://drive.google.com/drive/folders/1-c9q3sV8BCZjtch0WqWnXnJWSE1il5uS",
            "English": "https://drive.google.com/drive/folders/1-VKypMW3rybYR_0dPrro1JscD8eGtj9u",
            "Hindi": "https://drive.google.com/drive/folders/1-Ud6Gv65aE25yPcul3cbprGvXZrXX2O0"
        },
        11: {
            "Science": {
                "Physics": "https://drive.google.com/drive/folders/100rYQz_YiMNnT7zK_dxW-t8PUYj7GABP",
                "Chemistry": "https://drive.google.com/drive/folders/10A46iQRdTn0AJGwBfsZ4TRZ_naTsGcJ2",
                "Math": "https://drive.google.com/drive/folders/1-yiJhKx6TVLZQ9DlHyvQLZli8N8Qd6TB",
                "Biology": "https://drive.google.com/drive/folders/1-lL_2Z5_4cvklYRMSv2vTWorip9w-RWx"
            }
        },
        12: {
            "Science": {
                "Physics": "https://drive.google.com/drive/folders/10QCZZ78wmLGERWwVoCnQysVOzizeervS",
                "Chemistry": "https://drive.google.com/drive/folders/10TlsfeqLn5PHarO3rclePp5bg6HBq4K4",
                "Math": "https://drive.google.com/drive/folders/10OfK1z06vhLqAhPnuYt4w7cN0rZDtbES",
                "Biology": "https://drive.google.com/drive/folders/10I1sPq0wvSMD8gNtaoFEFFvtQ3fZSDIF"
            }
        }
    };

    function showPage(page) {
        document.getElementById(`${currentPage}Container`).classList.add('hidden');
        document.getElementById(`${page}Container`).classList.remove('hidden');
        document.getElementById('backButton').style.display = (page !== 'class') ? 'block' : 'none';
        currentPage = page;
    }

    function selectClass(cls) {
        selectedClass = cls;
        if (cls <= 10) {
            loadSubjects(cls);
        } else {
            showPage('stream');
        }
    }

    function selectStream(stream) {
        selectedStream = stream;
        loadSubjects(selectedClass);
    }

    function loadSubjects(cls) {
        const subjectsList = document.getElementById('subjectsList');
        subjectsList.innerHTML = '';

        const subjects = cls <= 10 ? subjectLinks[cls] : subjectLinks[cls][selectedStream];

        for (const [subject, link] of Object.entries(subjects)) {
            subjectsList.innerHTML += `
                <div class="option">
                    ${subject}
                    <button class="access-button" onclick="window.open('${link}', '_blank')">Access to Notes</button>
                </div>
            `;
        }

        showPage('subject');
    }

    function goBack() {
        showPage(currentPage === 'subject' ? (selectedClass > 10 ? 'stream' : 'class') : 'class');
    }
</script>

</body>
</html>


