<!DOCTYPE html>
<html>
<head>
    <title>Lovers Quiz 💌</title>
    <style>
        body {
            background-color: #fff0f5;
            font-family: 'Comic Sans MS', cursive;
            text-align: center;
            padding: 50px;
        }
        h1 {
            color: #ff3399;
        }
        .question {
            font-size: 24px;
            color: #cc0066;
            margin-bottom: 20px;
        }
        .option {
            background-color: #ff66b3;
            border: none;
            color: white;
            padding: 10px 20px;
            font-size: 18px;
            border-radius: 10px;
            cursor: pointer;
            margin: 5px;
        }
        .option:hover {
            background-color: #ff3399;
        }
        #answer {
            margin-top: 30px;
            font-size: 22px;
            color: #cc0066;
        }
        #nextBtn {
            margin-top: 20px;
            padding: 10px 25px;
            font-size: 18px;
            background-color: #ff66b3;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
        }
        #nextBtn:hover {
            background-color: #ff3399;
        }
    </style>
</head>
<body>
    <h1>Lovers Quiz 💖</h1>
    
    <div class="question" id="question"></div>
    <div id="options"></div>
    <div id="answer"></div>
    <button id="nextBtn" onclick="nextQuestion()" style="display:none;">Next Question ➡️</button>
    
    <script>
        const quizQuestions = [
            {
                question: "When did we first meet? 🌸",
                options: ["Last year", "2 years ago", "3 years ago", "Not sure 😅", "1 year ago"],
                correct: "1 year ago"
            },
            {
                question: "What's our anniversary date? 🎉",
                options: ["Jan 1", "Feb 14", "Mar 20", "Dec 25", "Aug 27"],
                correct: "Aug 27"
            },
            {
                question: "What's your favorite surprise I've given? 🎁",
                options: ["Flowers 🌹", "Chocolate 🍫", "Dinner 🍽️", "Trip ✈️", "Love", "Kiss"],
                correct: "Kiss"
            },
            {
                question: "What's your favorite food? 🍕",
                options: ["Pizza 🍕", "Burger 🍔", "Ice Cream 🍨", "Chocolate 🍫"],
                correct: "Chocolate 🍫"
            },
            {
                question: "What's your favorite music? 🎶",
                options: ["Pop", "Rock", "Classical", "Romantic"],
                correct: "Romantic"
            },
            {
                question: "What do you like about me?",
                options: ["Smile", "Style", "Hair"],
                correct: "Smile"
            },
            {
                question: "Where did we meet first?",
                options: ["Bus", "Temple", "College"],
                correct: "College"
            },
            {
                question: "Who said love first?",
                options: ["You", "Me"],
                correct: "Me"
            },
            {
                question: "Who cares most?",
                options: ["You", "Me"],
                correct: "Me"
            }
        ];

        let currentQ = 0;

        function displayQuestion() {
            const q = quizQuestions[currentQ];
            document.getElementById("question").textContent = q.question;

            const optionsDiv = document.getElementById("options");
            optionsDiv.innerHTML = ""; // Clear previous options
            q.options.forEach(option => {
                const btn = document.createElement("button");
                btn.textContent = option;
                btn.classList.add("option");
                btn.onclick = () => checkAnswer(option);
                optionsDiv.appendChild(btn);
            });

            document.getElementById("answer").textContent = "";
            document.getElementById("nextBtn").style.display = "none";
        }

        function checkAnswer(selected) {
            const answerDiv = document.getElementById("answer");
            const correct = quizQuestions[currentQ].correct;
            if(selected === correct) {
                answerDiv.textContent = "Yay! You chose the right answer 😘💖";
            } else {
                answerDiv.textContent = "Aww, you chose " + selected + " 😄💖";
            }
            document.getElementById("nextBtn").style.display = "inline-block";
        }

        function nextQuestion() {
            currentQ++;
            if(currentQ < quizQuestions.length) {
                displayQuestion();
            } else {
                document.getElementById("question").textContent = "🎉 Quiz Completed! 😘💖";
                document.getElementById("options").innerHTML = "";
                document.getElementById("answer").textContent = "Thanks for playing!";
                document.getElementById("nextBtn").style.display = "none";
            }
        }

        // Initialize first question
        displayQuestion();
    </script>
</body>
</html>
