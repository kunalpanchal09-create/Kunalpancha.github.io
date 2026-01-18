# Kunalpancha.github.io
Website for students of class-10
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Student Helper AI</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<header>
    <h1>📘 Student Helper AI</h1>
    <p>Ask any study question (Class 6–12)</p>
</header>

<main>
    <div class="chat-box" id="chatBox"></div>

    <div class="input-area">
        <input type="text" id="userInput" placeholder="Ask a question...">
        <button onclick="sendMessage()">Ask</button>
    </div>
</main>

<footer>
    <p>Made for students • Free • No login</p>
</footer>

<script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background: #f4f6fb;
    margin: 0;
}

header {
    background: #4a6cf7;
    color: white;
    padding: 15px;
    text-align: center;
}

main {
    max-width: 600px;
    margin: auto;
    padding: 10px;
}

.chat-box {
    background: white;
    height: 350px;
    overflow-y: auto;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.message {
    margin: 10px 0;
}

.user {
    text-align: right;
    color: #333;
}

.bot {
    text-align: left;
    color: #4a6cf7;
}

.input-area {
    display: flex;
    margin-top: 10px;
}

input {
    flex: 1;
    padding: 10px;
    font-size: 16px;
}

button {
    background: #4a6cf7;
    color: white;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
}

button:hover {
    background: #3a5ae0;
}

footer {
    text-align: center;
    font-size: 14px;
    margin-top: 15px;
    color: #666;
}
const chatBox = document.getElementById("chatBox");

function sendMessage() {
    const input = document.getElementById("userInput");
    const question = input.value.trim();
    if (question === "") return;

    addMessage(question, "user");
    input.value = "";

    setTimeout(() => {
        const answer = aiResponse(question.toLowerCase());
        addMessage(answer, "bot");
    }, 600);
}

function addMessage(text, type) {
    const div = document.createElement("div");
    div.className = `message ${type}`;
    div.innerText = text;
    chatBox.appendChild(div);
    chatBox.scrollTop = chatBox.scrollHeight;
}

function aiResponse(q) {

    if (q.includes("ethanol") && q.includes("kmno4")) {
        return "Ethanol reacts with alkaline KMnO₄ to form ethanoic acid. This is an oxidation reaction.";
    }

    if (q.includes("pythagoras")) {
        return "Pythagoras theorem: In a right-angled triangle, (Hypotenuse)² = (Base)² + (Perpendicular)².";
    }

    if (q.includes("homologous series")) {
        return "A homologous series is a group of organic compounds having similar chemical properties and the same general formula.";
    }

    if (q.includes("career")) {
        return "Choose a career based on your skills, interests, and future scope. Technology, healthcare, and AI have strong demand.";
    }

    if (q.includes("formula")) {
        return "Tell me the chapter or topic and I will give you the correct formula.";
    }

    if (q.includes("math")) {
        return "Math tip: Practice daily, focus on formulas, and solve previous year questions.";
    }

    return "I am a student helper AI 🤖. Ask questions from science, maths, or career guidance.";
}
