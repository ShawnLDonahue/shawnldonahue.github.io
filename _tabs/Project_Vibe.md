<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Vibe Coded: Ubuntu Speedrun Terminal</title>
<style>
    body {
        background: #0b0f0c;
        color: #33ff66;
        font-family: monospace;
        margin: 0;
        padding: 20px;
    }

    #terminal {
        max-width: 900px;
        margin: auto;
        background: rgba(0,0,0,0.6);
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 20px rgba(0,255,100,0.2);
    }

    .line {
        margin: 5px 0;
    }

    input {
        width: 100%;
        background: black;
        border: 1px solid #33ff66;
        color: #33ff66;
        padding: 10px;
        font-family: monospace;
        outline: none;
    }

    .prompt {
        color: #00ffcc;
    }

    .error {
        color: #ff5555;
    }

    .success {
        color: #55ff55;
    }
</style>
</head>

<body>
<div id="terminal">
    <div class="line">Welcome to Ubuntu Command Speedrun Training</div>
    <div class="line">User: AmnesiaFree@UbuntuMachine</div>
    <div class="line">Type the correct command when prompted.</div>
    <div class="line">--------------------------------------------------</div>

    <div id="output"></div>

    <input id="input" placeholder="Enter command..." autofocus />
</div>

<script>
const questions = [
    {q:"Show current directory", a:"pwd"},
    {q:"List files in directory", a:"ls"},
    {q:"Change directory to /etc", a:"cd /etc"},
    {q:"Go up one directory", a:"cd .."},
    {q:"Create a directory named test", a:"mkdir test"},
    {q:"Remove file named file.txt", a:"rm file.txt"},
    {q:"Move file.txt to /tmp", a:"mv file.txt /tmp"},
    {q:"Copy file.txt to file2.txt", a:"cp file.txt file2.txt"},
    {q:"Show running processes", a:"ps"},
    {q:"Kill process with PID 1234", a:"kill 1234"},
    {q:"Show disk usage", a:"df -h"},
    {q:"Show memory usage", a:"free -h"},
    {q:"Print file contents", a:"cat file.txt"},
    {q:"Search for 'error' in file.log", a:"grep error file.log"},
    {q:"Find file named test.txt", a:"find . -name test.txt"},
    {q:"Show network interfaces", a:"ip a"},
    {q:"Show active connections", a:"netstat"},
    {q:"Update package list", a:"sudo apt update"},
    {q:"Install nginx", a:"sudo apt install nginx"},
    {q:"Change file permissions to 755", a:"chmod 755 file.sh"}
];

let roundQuestions = [];
let current = 0;
let score = 0;

const output = document.getElementById("output");
const input = document.getElementById("input");

function log(text, cls="line"){
    const div = document.createElement("div");
    div.className = cls;
    div.textContent = text;
    output.appendChild(div);
    window.scrollTo(0, document.body.scrollHeight);
}

function shuffle(arr){
    return arr.sort(() => Math.random() - 0.5);
}

function startRound(){
    roundQuestions = shuffle([...questions]).slice(0,10);
    current = 0;
    score = 0;
    log("--------------------------------------------------");
    log("New Speedrun Round Started");
    nextQuestion();
}

function nextQuestion(){
    if(current >= roundQuestions.length){
        endRound();
        return;
    }
    log(`Task ${current+1}: ${roundQuestions[current].q}`, "prompt");
}

function normalize(cmd){
    return cmd.trim().replace(/\s+/g,' ');
}

function endRound(){
    let percent = (score / roundQuestions.length) * 100;

    log("--------------------------------------------------");
    log(`Round complete. Score: ${score}/${roundQuestions.length} (${percent.toFixed(0)}%)`);

    if(percent >= 60){
        log("SUCCESS: You’ve passed the Ubuntu Speedrun!", "success");
        log("Type 'run' to play again.");
    } else {
        log("FAILED: Below 60%. Training extension triggered...", "error");
        log("Generating new 10-question drill...");
        setTimeout(startRound, 1500);
    }
}

input.addEventListener("keydown", function(e){
    if(e.key === "Enter"){
        let value = normalize(input.value);
        input.value = "";

        if(value === "run"){
            startRound();
            return;
        }

        if(current < roundQuestions.length){
            let correct = roundQuestions[current].a;

            if(value === correct){
                log("✔ Correct", "success");
                score++;
            } else {
                log(`✖ Wrong. Correct: ${correct}`, "error");
            }

            current++;
            nextQuestion();
        }
    }
});

log("Type 'run' to start the Ubuntu Speedrun.");
</script>

</body>
</html>