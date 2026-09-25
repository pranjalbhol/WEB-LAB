**PRG 1**
<!DOCTYPE html>
<html>
<head><title>Arun - Personal Webpage</title></head>
<body>
  <h1>Arun</h1>
  <p>Web Developer, Tech Enthusiast, and Coffee Lover</p>
  <img src="">
  
  <h2>About Me</h2>
  <p>Hello! I am Arun, a passionate developer learning how to build clean and responsive websites. I love exploring new technologies and solving creative problems.</p>
  
  <h2>Skills & Interests</h2>
  <p>Here are a few technologies I work with:</p>
  <ul>
    <li>HTML5 & CSS3</li><li>JavaScript (ES6+)</li><li>Git & GitHub</li><li>PHP & MYSQL</li>
  </ul>
  <p>My favorite hobbies:</p>
  <ol>
    <li>Playing Football</li><li>Bike Rally</li><li>Sky Gazing</li>
  </ol>

  <h2>Education & Experience</h2>
  <table border="1">
    <tr><th>Year</th><th>Role / Degree</th><th>Institution / Company</th></tr>
    <tr><td>2021 - Present</td><td>Frontend Developer</td><td>PresiTech Solutions Inc.</td></tr>
    <tr><td>2018 - 2021</td><td>Bachelor of Computer Application</td><td>Presidency College</td></tr>
  </table>

  <h2>My Favorite Media</h2>
  <h3>Sample Audio</h3>
  <audio controls src="......."></audio>

  <h3>Sample Video</h3>
  <video controls width="400" src=""></video>
</body>
</html>



**PRG 2**
<!DOCTYPE html>
<html>
<head>
<title>Responsive Web Page</title>
<style>
  body{font-family:Arial,sans-serif;background:#f4f4f4;color:#333;line-height:1.6;margin:0;}
  header{background:linear-gradient(to right,#0078d7,#00b4db);color:#fff;text-align:center;padding:30px;}
  header h1{margin-bottom:10px;}
  .container{display:flex;gap:20px;padding:20px;}
  .content{flex:3;background:#fff;padding:20px;border-radius:8px;}
  .sidebar{flex:1;background:#fff;padding:20px;border-radius:8px;}
  .content h2,.sidebar h3{color:#0078d7;margin-bottom:10px;}
  footer{text-align:center;padding:10px;}
  @media(max-width:600px){.container{flex-direction:column;}}
</style>
</head>
<body>
<header>
  <h1>Responsive Web Page</h1>
  <p>Designed using CSS3 Properties</p>
</header>
<ul>
  <li>#Home</li><li>#Services</li><li>#Gallery</li><li>#Contact</li>
</ul>
<div class="container">
  <section class="content">
    <h2>Welcome</h2>
    <p>This page demonstrates CSS3 features including colors, gradients, padding, margins, text formatting, alignment, hover effects, and responsive layouts.</p>
  </section>
  <aside class="sidebar">
    <h3>Latest Updates</h3>
    <p>Responsive design ensures the webpage adapts smoothly across desktops, tablets, and mobile devices.</p>
  </aside>
</div>
<footer><p>&copy; 2026 Responsive Web Design Example</p></footer>
</body>
</html>


**PRG 4**
<html>
<head>
<title>JavaScript Concept</title</title>
<script type="text/JavaScript">
	function concepts()
	{
		const a=[12,43,65,13,89,46, 14,3];
		document.write("<h1>Array elements are</h1>");
		for(i=0;i<8;i++)
			document.write("<h3>" + a[i] + "</h3>");
		var small=a[0];
		var large=a[0];
		for(i=0;i<8;i++)
		{
			if(a[i]>large) 
				large=a[i];
			if(a[i]<small) 
				small=a[i];
		}
		document.write("<h2> Largest element: " + large + "</h2>");
		document.write("<h2> Smallest element: " + small + "</h2>");
	}
</script>
</head>
<body onload="concepts()">
</body>


**PRG 5**
<!DOCTYPE html>
<html>
<head>
  <title>Dynamic DOM Page</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; transition: background-color .5s; padding: 50px; background: #f4f4f9; color: #333; }
    .card { background: #fff; padding: 20px; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,.1); max-width: 400px; margin: 0 auto; }
    img { width: 100%; height: 250px; object-fit: cover; border-radius: 8px; }
    button { margin-top: 20px; padding: 10px 20px; font-size: 16px; background: #007BFF; color: #fff; border: none; border-radius: 5px; cursor: pointer; }
  </style>
</head>
<body>
  <div class="card">
    <h1 id="t">Welcome to the Dynamic Page</h1>
    <p id="d">Click the button below to change the style, text, and image.</p>
    <img id="img" src="https://picsum.photos" alt="Scenic View"><br>
    <button onclick="change()">Change Content</button>
  </div>
  <script>
    const data = [
      ["Explore the Mountains", "High peaks and fresh crisp air.", "mountain.jpg", "#e3f2fd"],
      ["Relax by the Ocean", "Calm waves and golden sandy beaches.", "ocean.jpg", "#e8f5e9"],
      ["Discover the Forest", "Tall green trees and quiet trails.", "forest.jpg", "#fff3e0"]
    ];
    let i = -1;
    function change() {
      i = (i + 1) % data.length;
      [t.textContent, d.textContent, img.src, document.body.style.backgroundColor] = data[i];
    }
  </script>
</body>
</html>



**PRG 6**
<!DOCTYPE html>
<html>
<head>
  <title>Form Validation Application</title>
  <script>
    const val = (id) => document.getElementById(id).value;
    const validateName = () => { if (val("username").length < 4) alert("Invalid name"); };
    const validateEmail = () => { if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(val("email"))) alert("Invalid email"); };
    const validatePhone = () => { if (!/^\d{10}$/.test(val("mobile"))) alert("Invalid phone number"); };
    const validatePassword = () => { if (val("password").length < 8) alert("Please check password"); };
    function verify() {
      if (!val("username") || !val("password") || !val("email") || !val("mobile"))
        alert("Please fill all the fields");
    }
  </script>
</head>
<body>
  <h2>Create Account</h2>
  <form id="regForm">
    <label for="username">Full Name</label> <input type="text" id="username" onblur="validateName()"><br/>
    <label for="email">Email Address</label> <input type="email" id="email" onblur="validateEmail()"><br/>
    <label for="mobile">Mobile Number</label> <input type="tel" id="mobile" onblur="validatePhone()"><br/>
    <label for="password">Password</label> <input type="password" id="password" onblur="validatePassword()"><br/>
    <button type="submit" onclick="verify()">Submit</button>
  </form>
</body>
</html>
