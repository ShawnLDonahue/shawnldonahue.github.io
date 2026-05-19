---
# the default layout is 'page'
icon: fa-solid fa-terminal
order: 6
---

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
    {q:"Change file permissions to 755", a:"chmod 755 file.sh"},

    // --- Expanded training pool ---

    {q:"Create an empty file named notes.txt", a:"touch notes.txt"},
    {q:"Display first 10 lines of file.txt", a:"head file.txt"},
    {q:"Display last 10 lines of file.txt", a:"tail file.txt"},
    {q:"View file contents one page at a time", a:"less file.txt"},
    {q:"Show who you are logged in as", a:"whoami"},
    {q:"Show system uptime", a:"uptime"},
    {q:"Clear the terminal screen", a:"clear"},
    {q:"Show current date and time", a:"date"},
    {q:"Show command history", a:"history"},
    {q:"Create a directory called logs", a:"mkdir logs"},

    {q:"Remove directory named test (empty)", a:"rmdir test"},
    {q:"Remove directory recursively named test", a:"rm -r test"},
    {q:"Force delete file named file.txt", a:"rm -f file.txt"},
    {q:"Move directory src to dst", a:"mv src dst"},
    {q:"Copy directory src to dst recursively", a:"cp -r src dst"},

    {q:"Change ownership of file.txt to user john", a:"sudo chown john file.txt"},
    {q:"Change file permissions to read/write/execute for all", a:"chmod 777 file.txt"},
    {q:"Add execute permission to file.sh", a:"chmod +x file.sh"},

    {q:"Show IP routing table", a:"ip route"},
    {q:"Ping google.com", a:"ping google.com"},
    {q:"Show open ports", a:"ss -tuln"},

    {q:"Search for process named nginx", a:"ps aux | grep nginx"},
    {q:"Kill process by name nginx", a:"pkill nginx"},

    {q:"Show system information", a:"uname -a"},
    {q:"Show CPU info", a:"lscpu"},
    {q:"Show block devices", a:"lsblk"},

    {q:"Install package curl", a:"sudo apt install curl"},
    {q:"Remove package nginx", a:"sudo apt remove nginx"},
    {q:"Upgrade installed packages", a:"sudo apt upgrade"},

    {q:"Show logged in users", a:"who"},
    {q:"Show last logins", a:"last"},

    {q:"Create symbolic link", a:"ln -s file1 link1"},
    {q:"Show disk space in human readable format", a:"df -h"},
    {q:"Show folder sizes", a:"du -sh *"},

    {q:"Find all .log files", a:"find . -name '*.log'"},
    {q:"Search text 'error' in logs recursively", a:"grep -r error ."},

    {q:"Restart nginx service", a:"sudo systemctl restart nginx"},
    {q:"Check status of nginx service", a:"sudo systemctl status nginx"},
    {q:"Enable nginx at boot", a:"sudo systemctl enable nginx"}
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