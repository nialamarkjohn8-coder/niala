  <script>
    let active="Dashboard", open=true;
  </script>

  <div class="layout">
  <header>
    <button on:click={()=>open=!open}>☰</button>
    <h1>IReply Inventory</h1>
  </header>

  <div class="body">
  {#if open}
  <aside>
    <li class:active={active=="Dashboard"} on:click={()=>active="Dashboard"}>Dashboard</li>
    <li class:active={active=="Users"} on:click={()=>active="Users"}>Users</li>
    <li class:active={active=="Settings"} on:click={()=>active="Settings"}>Settings</li>
  </aside>
  {/if}

  <main>
  {#if active=="Dashboard"}
  <h2>Office Materials</h2>
  <div class="cards">
    <div class="card laptop">💻 Laptops</div>
    <div class="card mouse">🖱️ Mouse</div>
    <div class="card tools">🛠️ Tools</div>
  </div>

  {:else if active=="Users"}
  <h2>User Management</h2>
  <div class="user">John Doe — Admin</div>
  <div class="user">Jane Smith — Staff</div>

  {:else}
  <h2>System Settings</h2>
  <label class="switch">
    <input type="checkbox" checked>
    <span></span>
  </label>
  <p>Notifications Enabled</p>
  {/if}
  </main>
  </div>
  </div>

  <style>
  *{margin:0;box-sizing:border-box;font-family:system-ui}
  .layout{
    height:100vh;background:#0b1220;color:#e5e7eb}
  header{
    display:flex;gap:1rem;align-items:center;
  background:#020617;padding:1.5rem;border-bottom:1px solid #1e293b}
  header button{
    font-size:1.4rem;background:none;border:0;color:#fff;cursor:pointer}
  .body{
    display:flex;height:calc(100vh - 80px)}
  aside{
    width:180px;background:#020617;padding:1rem}
  aside li{
    list-style:none;padding:.7rem;cursor:pointer;border-radius:6px}
  aside li.active{
    background:#1e293b;font-weight:bold}
  main{
    flex:1;padding:2rem;background:#0f172a}
  .cards{
    display:flex;gap:1rem;margin-top:1.5rem}
  .card{
    flex:1;padding:2rem;border-radius:14px;
  text-align:center;font-weight:600;cursor:pointer;
  transition:.25s}
  .card:hover{
    transform:translateY(-4px)}
  .laptop{
    background:#0c1f3a;border:1px solid #2563eb}
  .mouse{
    background:#0b2a22;border:1px solid #16a34a}
  .tools{
    background:#2a1a0b;border:1px solid #f59e0b}
  .user{
    background:#0c2057;padding:1rem;margin:.5rem 0;border-radius:8px}
  .switch{
    position:relative;display:inline-block;width:50px;height:24px}
  .switch input{
    display:none}
  .switch span{
    position:absolute;inset:0;background:#334155;border-radius:24px}
  .switch span:before{
    content:"";position:absolute;width:18px;height:18px;
  left:3px;bottom:3px;background:#fff;border-radius:50%;transition:.2s}
  input:checked+span{
    background:#16a34a}
  input:checked+span:before{
    transform:translateX(26px)}
  </style>