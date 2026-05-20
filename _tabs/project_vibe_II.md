---
# the default layout is 'page'
icon: fa-solid fa-terminal
order: 7
---
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Project_Vibe II — Security Ops Dashboard</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root {
  --bg: #0f1217;
  --panel: #161b22;
  --border: #22272e;
  --text: #e6edf3;
  --muted: #9da7b3;
  --accent: #3fb950;
  --danger: #f85149;
}

* {
  box-sizing: border-box;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Ubuntu, sans-serif;
}

body {
  margin: 0;
  background: var(--bg);
  color: var(--text);
}

/* Header */
header {
  padding: 20px 30px;
  border-bottom: 1px solid var(--border);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header h1 {
  margin: 0;
  font-size: 20px;
  font-weight: 600;
}

#datetime {
  font-size: 14px;
  color: var(--muted);
}

/* Layout */
.dashboard {
  padding: 30px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 20px;
}

/* Panels */
.panel {
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 20px;
}

.panel h2 {
  margin-top: 0;
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 15px;
}

/* Availability table */
.availability {
  grid-column: 1 / -1;
}

.availability table {
  width: 100%;
  border-collapse: collapse;
  font-size: 14px;
}

.availability th,
.availability td {
  padding: 10px;
  text-align: left;
  border-bottom: 1px solid var(--border);
}

.availability th {
  color: var(--muted);
  font-weight: 500;
}

.status-light {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  display: inline-block;
}

.green {
  background: var(--accent);
}

.red {
  background: var(--danger);
}

select {
  background: var(--bg);
  color: var(--text);
  border: 1px solid var(--border);
  border-radius: 6px;
  padding: 4px 6px;
}

/* Lists */
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

li {
  padding: 8px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid var(--border);
}

li:last-child {
  border-bottom: none;
}

li span {
  outline: none;
}

/* Buttons */
button {
  background: none;
  border: none;
  color: var(--muted);
  cursor: pointer;
  font-size: 14px;
}

button:hover {
  color: var(--text);
}

.add-btn {
  margin-top: 12px;
  color: var(--accent);
  font-size: 14px;
}

/* Links */
a {
  color: #58a6ff;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

/* Footer */
.footer-note {
  text-align: center;
  padding: 20px;
  color: var(--muted);
  font-size: 12px;
}
</style>
</head>

<body>

<header>
  <h1>Project_Vibe II — Security Operations Dashboard</h1>
  <div id="datetime"></div>
</header>

<main class="dashboard">

  <!-- Team Availability -->
  <section class="panel availability">
    <h2>Team Availability</h2>
    <table>
      <thead>
        <tr>
          <th>Role</th>
          <th>Last Change</th>
          <th>Reason</th>
          <th>Status</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Manager</td>
          <td class="timestamp">—</td>
          <td>
            <select onchange="updateStatus(this)">
              <option value="green">Available</option>
              <option value="red">Lunch</option>
              <option value="red">Break</option>
              <option value="red">Personal</option>
              <option value="red">DND</option>
              <option value="red">Meeting</option>
              <option value="red">Focus</option>
              <option value="red">Project</option>
            </select>
          </td>
          <td><span class="status-light green"></span></td>
        </tr>

        <tr>
          <td>Senior</td>
          <td class="timestamp">—</td>
          <td>
            <select onchange="updateStatus(this)">
              <option value="green">Available</option>
              <option value="red">Lunch</option>
              <option value="red">Break</option>
              <option value="red">Personal</option>
              <option value="red">DND</option>
              <option value="red">Meeting</option>
              <option value="red">Focus</option>
              <option value="red">Project</option>
            </select>
          </td>
          <td><span class="status-light green"></span></td>
        </tr>

        <tr>
          <td>Junior</td>
          <td class="timestamp">—</td>
          <td>
            <select onchange="updateStatus(this)">
              <option value="green">Available</option>
              <option value="red">Lunch</option>
              <option value="red">Break</option>
              <option value="red">Personal</option>
              <option value="red">DND</option>
              <option value="red">Meeting</option>
              <option value="red">Focus</option>
              <option value="red">Project</option>
            </select>
          </td>
          <td><span class="status-light green"></span></td>
        </tr>

        <tr>
          <td>Contractor I</td>
          <td class="timestamp">—</td>
          <td>
            <select onchange="updateStatus(this)">
              <option value="green">Available</option>
              <option value="red">Lunch</option>
              <option value="red">Break</option>
              <option value="red">Personal</option>
              <option value="red">DND</option>
              <option value="red">Meeting</option>
              <option value="red">Focus</option>
              <option value="red">Project</option>
            </select>
          </td>
          <td><span class="status-light green"></span></td>
        </tr>

        <tr>
          <td>Contractor II</td>
          <td class="timestamp">—</td>
          <td>
            <select onchange="updateStatus(this)">
              <option value="green">Available</option>
              <option value="red">Lunch</option>
              <option value="red">Break</option>
              <option value="red">Personal</option>
              <option value="red">DND</option>
              <option value="red">Meeting</option>
              <option value="red">Focus</option>
              <option value="red">Project</option>
            </select>
          </td>
          <td><span class="status-light green"></span></td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- Active Projects -->
  <section class="panel">
    <h2>Active Projects</h2>
    <ul id="activeProjects">
      <li><span contenteditable="true">Incident Response Plan Refresh</span><button onclick="removeItem(this)">✕</button></li>
      <li><span contenteditable="true">Vulnerability Scan Review</span><button onclick="removeItem(this)">✕</button></li>
    </ul>
    <button class="add-btn" onclick="addItem('activeProjects')">+ Add Project</button>
  </section>

  <!-- Backlog -->
  <section class="panel">
    <h2>Backlog / Not Started</h2>
    <ul id="backlog">
      <li><span contenteditable="true">SIEM Rule Optimization</span><button onclick="removeItem(this)">✕</button></li>
      <li><span contenteditable="true">Tabletop Exercise Planning</span><button onclick="removeItem(this)">✕</button></li>
    </ul>
    <button class="add-btn" onclick="addItem('backlog')">+ Add Item</button>
  </section>

  <!-- Documentation -->
  <section class="panel">
    <h2>Security Documentation</h2>
    <ul id="docs">
      <li><span contenteditable="true"><a href="#" onclick="return false;">Incident Response Playbook</a></span><button onclick="removeItem(this)">✕</button></li>
      <li><span contenteditable="true"><a href="#" onclick="return false;">Policies & Standards</a></span><button onclick="removeItem(this)">✕</button></li>
      <li><span contenteditable="true"><a href="#" onclick="return false;">Network Forensics Runbook</a></span><button onclick="removeItem(this)">✕</button></li>
    </ul>
    <button class="add-btn" onclick="addItem('docs')">+ Add Document</button>
  </section>

</main>

<div class="footer-note">
  Prototype dashboard • No data persistence by design
</div>

<script>
function updateDateTime() {
  const now = new Date();
  document.getElementById("datetime").textContent =
    now.toLocaleDateString(undefined, { weekday: 'long', year: 'numeric', month: 'short', day: 'numeric' }) +
    " • " +
    now.toLocaleTimeString();
}

setInterval(updateDateTime, 1000);
updateDateTime();

function addItem(listId) {
  const ul = document.getElementById(listId);
  const li = document.createElement("li");
  li.innerHTML = `<span contenteditable="true">New item</span><button onclick="removeItem(this)">✕</button>`;
  ul.appendChild(li);
}

function removeItem(btn) {
  btn.parentElement.remove();
}

function updateStatus(select) {
  const row = select.closest("tr");
  const light = row.querySelector(".status-light");
  const timestamp = row.querySelector(".timestamp");

  light.className = "status-light " + select.value;

  const now = new Date();
  timestamp.textContent = now.toLocaleString();
}
</script>

</body>
</html>