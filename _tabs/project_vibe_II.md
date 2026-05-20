---
# the default layout is 'page'
icon: fa-solid fa-terminal
order: 7
---
<div id="project-vibe-ii">

  <header class="pv-header">
    <h1>Project_Vibe II — Security Operations Dashboard</h1>
    <div id="pv-datetime"></div>
  </header>

  <main class="pv-dashboard">

    <!-- Team Availability -->
    <section class="pv-panel pv-availability">
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
            <td class="pv-timestamp">—</td>
            <td>
              <select onchange="pvUpdateStatus(this)">
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
            <td><span class="pv-status pv-green"></span></td>
          </tr>

          <tr>
            <td>Senior</td>
            <td class="pv-timestamp">—</td>
            <td>
              <select onchange="pvUpdateStatus(this)">
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
            <td><span class="pv-status pv-green"></span></td>
          </tr>

          <tr>
            <td>Junior</td>
            <td class="pv-timestamp">—</td>
            <td>
              <select onchange="pvUpdateStatus(this)">
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
            <td><span class="pv-status pv-green"></span></td>
          </tr>

          <tr>
            <td>Contractor I</td>
            <td class="pv-timestamp">—</td>
            <td>
              <select onchange="pvUpdateStatus(this)">
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
            <td><span class="pv-status pv-green"></span></td>
          </tr>

          <tr>
            <td>Contractor II</td>
            <td class="pv-timestamp">—</td>
            <td>
              <select onchange="pvUpdateStatus(this)">
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
            <td><span class="pv-status pv-green"></span></td>
          </tr>
        </tbody>
      </table>
    </section>

  </main>

</div>

<script>
(function () {
  const style = document.createElement("style");
  style.innerHTML = `
  #project-vibe-ii {
    --bg:#0f1217;--panel:#161b22;--border:#22272e;
    --text:#e6edf3;--muted:#9da7b3;
    --green:#3fb950;--red:#f85149;
    color:var(--text);
    font-family:system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Ubuntu,sans-serif;
  }
  .pv-header{display:flex;justify-content:space-between;align-items:center;padding:20px;border-bottom:1px solid var(--border)}
  .pv-header h1{margin:0;font-size:20px;font-weight:600}
  #pv-datetime{font-size:14px;color:var(--muted)}
  .pv-dashboard{padding:20px}
  .pv-panel{background:var(--panel);border:1px solid var(--border);border-radius:10px;padding:20px}
  .pv-panel h2{margin-top:0;font-size:16px}
  table{width:100%;border-collapse:collapse;font-size:14px}
  th,td{padding:10px;border-bottom:1px solid var(--border);text-align:left}
  th{color:var(--muted);font-weight:500}
  select{background:var(--bg);color:var(--text);border:1px solid var(--border);border-radius:6px;padding:4px}
  .pv-status{width:14px;height:14px;border-radius:50%;display:inline-block}
  .pv-green{background:var(--green)}
  .pv-red{background:var(--red)}
  `;
  document.head.appendChild(style);

  window.pvUpdateStatus = function (select) {
    const row = select.closest("tr");
    const ts = row.querySelector(".pv-timestamp");
    const light = row.querySelector(".pv-status");

    const now = new Date();
    ts.textContent = now.toLocaleString();

    light.classList.remove("pv-green","pv-red");
    light.classList.add(select.value === "green" ? "pv-green" : "pv-red");
  };

  function updateClock() {
    const el = document.getElementById("pv-datetime");
    if (!el) return;
    const now = new Date();
    el.textContent = now.toLocaleDateString(undefined,{
      weekday:"long",year:"numeric",month:"short",day:"numeric"
    }) + " • " + now.toLocaleTimeString();
  }

  updateClock();
  setInterval(updateClock, 1000);
})();
</script>