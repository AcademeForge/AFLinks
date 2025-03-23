<!-- Class Selection Page -->
<div class="container hidden" id="classContainer">
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
    let currentPage = 'login';
    let selectedClass = null;
    let selectedStream = null;

    // Define subject links for all classes and streams (PLACEHOLDERS)
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
            },
            "Commerce": {
                "Business Studies": "https://drive.google.com/drive/folders/10hbeBCGpwKV8AJlMLN-gkT8ROL-mPJnL", 
                "Accountancy": "https://drive.google.com/drive/folders/10bQ9TYUr2qS3U5rerp5UMyX3qnzF1N2o", 
                "Economics": "https://drive.google.com/drive/folders/10akiwYES3pDVQoPfTHiGJUZ_y9z7J6sx" 
            },
            "Arts": {
                "History": "https://drive.google.com/drive/folders/11HZgkLXZWY391tQnU6mAkyepSHH7BnwD", 
                "Political Science": "https://drive.google.com/drive/folders/11McG2nZBPwTOQivoYRLnuHDrCTaxZfDj", 
                "Economics": "https://drive.google.com/drive/folders/11Mz2f1dukzNn7zqNA8FATyQuvDS3to4Z", 
                "Psychology": "https://drive.google.com/drive/folders/11OHqx9uiW0po8Jb7EqCDOgy_hNpQa8OH", 
                "Geography": "https://drive.google.com/drive/folders/11OHXiJxjOtqmN0yg_TeqUg8hJEU4nkbk"
            }
        },
        12: {
            "Science": {
                "Physics": "https://drive.google.com/drive/folders/10QCZZ78wmLGERWwVoCnQysVOzizeervS", 
                "Chemistry": "https://drive.google.com/drive/folders/10TlsfeqLn5PHarO3rclePp5bg6HBq4K4", 
                "Math": "https://drive.google.com/drive/folders/10OfK1z06vhLqAhPnuYt4w7cN0rZDtbES", 
                "Biology": "https://drive.google.com/drive/folders/10I1sPq0wvSMD8gNtaoFEFFvtQ3fZSDIF" 
            },
            "Commerce": {
                "Business Studies": "https://drive.google.com/drive/folders/114ncGbXaaDS_Uq_jFZ6S8XvUPxGqUomy", 
                "Accountancy": "https://drive.google.com/drive/folders/1133qJ8A91II5MwG9dJMeyQxgF88GEJe6", 
                "Economics": "https://drive.google.com/drive/folders/10zTfWiTZEjnip9jQ4_NQ5D-iKdgC2I8z" 
            },
            "Arts": {
                "History": "https://drive.google.com/drive/folders/11gfrxRKkwZg9yEREvyS06N6zNGH4QFRi", 
                "Political Science": "https://drive.google.com/drive/folders/11c9BDCtzO6OjZumMYlXhklSfwJud5D9z", 
                "Economics": "https://drive.google.com/drive/folders/11jMqr1owMcbXsVci7CgYbyyfWrb3zgtd", 
                "Psychology": "https://drive.google.com/drive/folders/11Y7G9_79zt197nQFMYgKpsKcAb99Ge7c", 
                "Geography": "https://drive.google.com/drive/folders/11XmaUWcoB2JPes05FONuxLtFbDIfSln0"
            }
        }
    };

    function showPage(page) {
        document.getElementById(`${currentPage}Container`).classList.add('hidden');
        document.getElementById(`${page}Container`).classList.remove('hidden');
        document.getElementById('backButton').style.display = (page !== 'login') ? 'block' : 'none';
        currentPage = page;
    }

    function login() {
        showPage('class');
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

        if (cls <= 10) {
            for (const [subject, link] of Object.entries(subjectLinks[cls])) {
                subjectsList.innerHTML += `
                    <div class="option">
                        ${subject}
                        <button class="access-button" onclick="window.open('${link}', '_blank')">Access to Notes</button>
                    </div>
                `;
            }
        } else {
            for (const [subject, link] of Object.entries(subjectLinks[cls][selectedStream])) {
                subjectsList.innerHTML += `
                    <div class="option">
                        ${subject}
                        <button class="access-button" onclick="window.open('${link}', '_blank')">Access to Notes</button>
                    </div>
                `;
            }
        }
        showPage('subject');
    }

    function goBack() {
        if (currentPage === 'subject') showPage(selectedClass > 10 ? 'stream' : 'class');
        else if (currentPage === 'stream') showPage('class');
        else if (currentPage === 'class') showPage('login');
    }
</script>

</body>
</html>