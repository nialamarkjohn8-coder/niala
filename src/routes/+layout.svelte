<script>
  let active = "Dashboard";
</script>

<div class="layout">
  <header class="header"><h1>IReply Inventory</h1></header>

  <div class="body">
    <aside class="sidebar">
      <ul>
        <li class:active={active==="Dashboard"} on:click={()=>active="Dashboard"}>Dashboard</li>
        <li class:active={active==="Users"} on:click={()=>active="Users"}>Users</li>
        <li class:active={active==="Settings"} on:click={()=>active="Settings"}>Settings</li>
      </ul>
    </aside>

    <main class="content">
      {#if active==="Dashboard"}
        <h2>Office Materials</h2>
        <div class="cards">
          <div class="card">💻 Laptops</div>
          <div class="card">🖱️ Mouse</div>
          <div class="card">🛠️ Tools</div>
        </div>
      {:else if active==="Users"}
        <h2>User Management</h2>
        <ul class="user-list">
          <li>John Doe — Admin</li>
          <li>Jane Smith — Staff</li>
        </ul>
      {:else if active==="Settings"}
        <div class="settings-box">
          <h2>System Settings</h2>
          <h3>Notifications</h3>
          <label class="switch">
            <input type="checkbox" checked />
            <span class="slider"></span>
          </label>
          <p>Enabled</p>
        </div>
      {/if}
    </main>
  </div>
</div>

<style>
*{box-sizing:border-box;font-family:system-ui,sans-serif}
.layout{
	display:flex;flex-direction:column;height:100vh;background:#0b1220;color:#e5e7eb}
.header{
	background:#020617;color:#f8fafc;padding:3rem 1.5rem;border-bottom:1px solid #1e293b}
.body{
	display:flex;flex:1}
.sidebar{
	width:180px;background:#020617;color:#cbd5e1;padding:1rem;border-right:1px solid #1e293b}
.sidebar ul{
	list-style:none;padding:0}
.sidebar li{
	cursor:pointer;padding:0.8rem;border-radius:6px}
.sidebar li.active{
	background:#1e293b;color:#f8fafc;font-weight:bold}
.content{
	flex:1;padding:2rem;background:#0f172a}
h1,h2,h3{color:#f8fafc}
.cards{
	display:flex;gap:1.5rem;margin-bottom:2rem}
.card{
	background:#0c2057;border:1px solid #1e293b;padding:5rem;border-radius:12px;flex:1;text-align:center;font-size:1.2rem}
.user-list li{
	background:#0c2057;border:1px solid #1e293b;padding:1rem;margin-bottom:0.75rem;border-radius:8px}
.settings-box{
	background:#0c2057;border:1px solid #1e293b;padding:1.5rem;border-radius:12px}
.switch{
	position:relative;width:50px;height:24px;display:inline-block}
.switch input{
	display:none}
.slider{
	position:absolute;inset:0;background:#334155;border-radius:24px;cursor:pointer}
.slider:before{
	content:"";position:absolute;width:18px;height:18px;left:3px;bottom:3px;background:white;border-radius:50%;transition:.2s}
/* Change notification switch color to green */
input:checked + .slider {
	background: #16a34a;
}
input:checked+.slider:before{transform:translateX(26px)}
</style>