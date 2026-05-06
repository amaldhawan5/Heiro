# Heiro
Helping people get hired in top companies 
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Career Hub Pro</title>
<style>
body {font-family: Arial; margin:0; background:#eef2f7;}
header {background:#0d6efd; color:white; padding:20px; text-align:center;}
nav {display:flex; justify-content:center; background:#222;}
nav button {background:none; border:none; color:white; padding:15px; cursor:pointer; font-size:16px;}
nav button:hover {background:#0d6efd;}
section {display:none; padding:20px;}
.active {display:block;}
input, textarea, select {width:100%; padding:10px; margin:8px 0;}
button {padding:10px; border:none; cursor:pointer; border-radius:5px;}
.primary {background:#0d6efd; color:white;}
.card {background:white; padding:15px; margin:10px 0; border-radius:10px; box-shadow:0 0 10px rgba(0,0,0,0.1);} 
</style>
</head>
<body><header>
<h1>Career Hub Pro</h1>
<p>Build Resume • Find Jobs • Apply Govt Exams</p>
</header><nav>
<button onclick="showSection('biodata')">Biodata Builder</button>
<button onclick="showSection('jobs')">Hiring Companies</button>
<button onclick="showSection('govt')">Govt Exams</button>
</nav><!-- BIODATA --><section id="biodata" class="active">
<h2>Create Professional Biodata</h2>
<input id="name" placeholder="Full Name">
<input id="email" placeholder="Email">
<input id="phone" placeholder="Phone Number">
<textarea id="address" placeholder="Address"></textarea>
<textarea id="skills" placeholder="Skills (comma separated)"></textarea>
<textarea id="education" placeholder="Education"></textarea>
<textarea id="experience" placeholder="Experience"></textarea>
<button class="primary" onclick="generateResume()">Generate Biodata</button>
<button onclick="downloadPDF()">Download as PDF</button><div id="resume" class="card"></div>
</section><!-- JOBS --><section id="jobs">
<h2>Companies Hiring</h2>
<div class="card">
<h3>TCS</h3>
<p>Roles: Developer, Analyst</p>
<a href="https://www.tcs.com/careers" target="_blank"><button class="primary">Apply</button></a>
</div>
<div class="card">
<h3>Infosys</h3>
<p>Roles: Engineer, Consultant</p>
<a href="https://www.infosys.com/careers" target="_blank"><button class="primary">Apply</button></a>
</div>
<div class="card">
<h3>Wipro</h3>
<p>Roles: IT Services, Support</p>
<a href="https://careers.wipro.com" target="_blank"><button class="primary">Apply</button></a>
</div>
</section><!-- GOVT --><section id="govt">
<h2>Government Exams</h2>
<div class="card">
<h3>UPSC Civil Services</h3>
<p>India's top administrative exam</p>
<a href="https://upsc.gov.in" target="_blank"><button class="primary">Register</button></a>
</div>
<div class="card">
<h3>SSC CGL</h3>
<p>Staff Selection Commission Graduate Level</p>
<a href="https://ssc.nic.in" target="_blank"><button class="primary">Register</button></a>
</div>
<div class="card">
<h3>IBPS Banking Exams</h3>
<p>Bank PO & Clerk exams</p>
<a href="https://www.ibps.in" target="_blank"><button class="primary">Register</button></a>
</div>
</section><script>
function showSection(id) {
 document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
 document.getElementById(id).classList.add('active');
}

function generateResume() {
 let name = document.getElementById('name').value;
 let email = document.getElementById('email').value;
 let phone = document.getElementById('phone').value;
 let address = document.getElementById('address').value;
 let skills = document.getElementById('skills').value;
 let education = document.getElementById('education').value;
 let experience = document.getElementById('experience').value;

 document.getElementById('resume').innerHTML = `
 <h2>${name}</h2>
 <p><b>Email:</b> ${email}</p>
 <p><b>Phone:</b> ${phone}</p>
 <p><b>Address:</b> ${address}</p>
 <h3>Skills</h3><p>${skills}</p>
 <h3>Education</h3><p>${education}</p>
 <h3>Experience</h3><p>${experience}</p>
 `;
}

function downloadPDF() {
 window.print();
}
</script></body>
</html>
