<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SPA Admin Dashboard</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Segoe UI, sans-serif;
}

body{
    display:flex;
    min-height:100vh;
    background:#f4f6fb;
}

/* Sidebar */
.sidebar{
    width:240px;
    background:linear-gradient(180deg,#4e73df,#224abe);
    color:white;
    padding:20px;
}

.sidebar h2{
    margin-bottom:30px;
}

.sidebar ul{
    list-style:none;
}

.sidebar ul li{
    padding:12px;
    margin:8px 0;
    border-radius:8px;
    cursor:pointer;
    transition:0.3s;
}

.sidebar ul li:hover,
.sidebar ul li.active{
    background:rgba(255,255,255,0.2);
}

/* Main Content */
.wrapper{
    flex:1;
    padding:20px;
}

/* Topbar */
.topbar{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:15px 20px;
    border-radius:12px;
    background:white;
    box-shadow:0 4px 15px rgba(0,0,0,0.1);
    margin-bottom:20px;
}

/* Page Sections */
.page{
    display:none;
    animation:fade 0.4s ease-in-out;
}

.page.active{
    display:block;
}

@keyframes fade{
    from{opacity:0; transform:translateY(10px);}
    to{opacity:1; transform:translateY(0);}
}

/* Cards */
.cards{
    display:flex;
    gap:20px;
    flex-wrap:wrap;
}

.card{
    flex:1 1 220px;
    padding:25px;
    border-radius:15px;
    background:white;
    box-shadow:0 8px 20px rgba(0,0,0,0.1);
}

table{
    width:100%;
    margin-top:20px;
    border-collapse:collapse;
}

table th, table td{
    padding:12px;
}

table th{
    background:#f1f1f1;
}

</style>
</head>

<body>

<div class="sidebar">
    <h2>ShivMart</h2>
    <ul>
        <li class="active" onclick="showPage('dashboard', this)">Dashboard</li>
        <li onclick="showPage('products', this)">Products</li>
        <li onclick="showPage('orders', this)">Orders</li>
        <li onclick="showPage('customers', this)">Customers</li>
        <li onclick="showPage('reports', this)">Reports</li>
        <li onclick="showPage('settings', this)">Settings</li>
    </ul>
</div>

<div class="wrapper">

    <div class="topbar">
        <h2 id="pageTitle">Dashboard</h2>
        <span>Welcome, Admin</span>
    </div>

    <!-- DASHBOARD PAGE -->
    <div id="dashboard" class="page active">
        <div class="cards">
            <div class="card">
                <h3>Total Revenue</h3>
                <p>₹2,40,000</p>
            </div>
            <div class="card">
                <h3>Total Orders</h3>
                <p>520</p>
            </div>
        </div>
    </div>

    <!-- PRODUCTS PAGE -->
    <div id="products" class="page">
        <h3>Product Management</h3>
        <table>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Price</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Laptop</td>
                <td>₹50,000</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Phone</td>
                <td>₹20,000</td>
            </tr>
        </table>
    </div>

    <!-- ORDERS PAGE -->
    <div id="orders" class="page">
        <h3>Orders</h3>
        <p>All customer orders appear here.</p>
    </div>

    <!-- CUSTOMERS PAGE -->
    <div id="customers" class="page">
        <h3>Customers</h3>
        <p>Customer details appear here.</p>
    </div>

    <!-- REPORTS PAGE -->
    <div id="reports" class="page">
        <h3>Reports</h3>
        <p>Sales reports and analytics here.</p>
    </div>

    <!-- SETTINGS PAGE -->
    <div id="settings" class="page">
        <h3>Settings</h3>
        <p>Admin settings configuration.</p>
    </div>

</div>

<script>
function showPage(pageId, element) {

    // Hide all pages
    document.querySelectorAll('.page').forEach(page => {
        page.classList.remove('active');
    });

    // Remove active class from menu
    document.querySelectorAll('.sidebar ul li').forEach(li => {
        li.classList.remove('active');
    });

    // Show selected page
    document.getElementById(pageId).classList.add('active');

    // Highlight active menu
    element.classList.add('active');

    // Change top title
    document.getElementById('pageTitle').innerText = element.innerText;
}
</script>

</body>
</html>
