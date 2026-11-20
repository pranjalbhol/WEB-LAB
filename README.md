**1. Personal webpage (HTML5)**
<!DOCTYPE html>
<html><head><meta charset="utf-8"><title>My Webpage</title></head><body>
<h1>My Webpage</h1>
<p>Hi, I am <b>Rahul</b>.</p>
<ul><li>Reading</li><li>Coding</li></ul>
<table border="1">
<tr><th>Degree</th><th>Year</th></tr>
<tr><td>BCA</td><td>2026</td></tr>
</table>
<img src="photo.jpg" width="150" alt="photo"><br>
<audio src="sample.mp3" controls></audio><br>
<video src="sample.mp4" width="300" controls></video><br>
<a href="https://google.com">Visit Google</a>
</body></html>

**2. Responsive page (CSS3)**
<!DOCTYPE html>
<html><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>CSS3 Page</title>
<style>
body{margin:0;font-family:Arial;background:#eee}
h1{background:navy;color:white;text-align:center;padding:20px;margin:0}
p{width:60%;margin:20px auto;padding:20px;background:white;text-align:justify;font-size:18px}
@media(max-width:600px){p{width:90%}}
</style>
</head><body>
<h1>CSS3 Page</h1>
<p>This page shows colors, backgrounds, margin, padding, text formatting and alignment.</p>
</body></html>

**4. JavaScript basics**
<!DOCTYPE html>
<html><head><meta charset="utf-8"><title>JS Basics</title></head><body>
<script>
let marks = [85, 72, 90], total = 0;
for (let m of marks) total += m;
let avg = total / marks.length;
document.write("Total: " + total + "<br>Average: " + avg.toFixed(2) + "<br>");
if (avg >= 80) document.write("Grade A");
else if (avg >= 60) document.write("Grade B");
else document.write("Fail");
</script>
</body></html>

**5. DOM manipulation**
<!DOCTYPE html>
<html>
<body>
<h1 id="heading">Hello Students!</h1>
<p id="message">This is the original content.</p>
<img id="pic" src="image1.jpg" width="200"><br><br>
<button onclick="change()">Click Me</button>
<script>
function change() {
heading.innerHTML = "Welcome to JavaScript!"; // content
message.innerHTML = "The content has been changed.";
document.body.style.backgroundColor = "lightblue"; // color
pic.src = "image2.jpg"; // image
}
</script>
</body>
</html>

**6. Form validation**
<!DOCTYPE html>
<html><head><meta charset="utf-8"><title>Form Validation</title></head><body>
<form onsubmit="return check()">
Name <input id="n"><br>
Email <input id="e"><br>
Mobile <input id="m"><br>
Password <input type="password" id="p"><br>
<button>Register</button>
</form>
<script>
function check() {
let v = id => document.getElementById(id).value, err = "";
if (v("n") == "") err = "Enter name";
else if (!/^\S+@\S+\.\S+$/.test(v("e"))) err = "Invalid email";
else if (!/^[6-9]\d{9}$/.test(v("m"))) err = "Invalid mobile";
else if (v("p").length < 8) err = "Password must be 8+ characters";
alert(err || "Registration successful!");
return false;
}
</script>
</body></html>

**7. Fetch API + JSON**
<!DOCTYPE html>
<html><head><meta charset="utf-8"><title>Fetch API + JSON</title></head><body>
<h2>Users</h2>
<ul id="list"></ul>
<script>
// Sample JSON stored inside the page, so no internet is needed
let json = JSON.stringify([
{name:"Leanne Graham", email:"Sincere@april.biz"},
{name:"Ervin Howell", email:"Shanna@melissa.tv"},
{name:"Clementine Bauch", email:"Nathan@yesenia.net"},
{name:"Patricia Lebsack", email:"Julianne.OConner@kory.org"},
{name:"Chelsey Dietrich", email:"Lucio_Hettinger@annie.ca"},
{name:"Dennis Schulist", email:"Karley_Dach@jasper.info"},
{name:"Kurtis Weissnat", email:"Telly.Hoeger@billy.biz"},
{name:"Nicholas Runolfsdottir", email:"Sherwood@rosamond.me"},
{name:"Glenna Reichert", email:"Chaim_McDermott@dana.io"},
{name:"Clementina DuBuque", email:"Rey.Padberg@karina.biz"}
]);
fetch("data:application/json," + encodeURIComponent(json))
.then(res => res.json())
.then(data => data.forEach(u =>
document.getElementById("list").innerHTML += `<li>${u.name} - ${u.email}</li>`))
.catch(() => document.getElementById("list").innerHTML =
"<li>Could not load</li>");
</script>
</body></html>

**8. XAMPP + basic PHP**
<?php
echo "Hello, World!<br>Welcome to PHP Programming";
?>

**9. Sessions, cookies & login**
<?php
session_start();
if ($_POST) {
$u = $_POST['u']; $p = $_POST['p'];
if ($u == "" || $p == "") echo "Fill all fields";
elseif ($u == "student" && $p == "1234") {
$_SESSION['u'] = $u;
setcookie("u", $u, time() + 3600);
echo "Welcome $u";
} else echo "Invalid login";
}
?>
<form method="post">
User <input name="u"><br>
Pass <input type="password" name="p"><br>
<button>Login</button>
</form>
<?php
if (isset($_SESSION['u'])) echo "Session: " . htmlspecialchars($_SESSION['u']) . "<br>";
if (isset($_COOKIE['u'])) echo "Cookie: " . htmlspecialchars($_COOKIE['u']);
?>
<p><small>Login: student / 1234. Cookie shows after the next reload.</small></p>

**10. MySQL CRUD**
Run in phpMyAdmin → SQL:
CREATE DATABASE college; USE college;
CREATE TABLE students(id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(50), course
VARCHAR(50));

<?php
$c = mysqli_connect("localhost","root","","college");
extract($_POST);
if (isset($insert)) mysqli_query($c,"INSERT INTO students(name,course)
VALUES('$name','$course')");
if (isset($update)) mysqli_query($c,"UPDATE students SET name='$name',
course='$course' WHERE id='$id'");
if (isset($delete)) mysqli_query($c,"DELETE FROM students WHERE id='$id'");
?>
<form method="post">
ID <input name="id"> Name <input name="name"> Course <input name="course"><br>
<button name="insert">Insert</button>
<button name="update">Update</button>
<button name="delete">Delete</button>
</form>
<table border="1">
<?php
$r = mysqli_query($c,"SELECT * FROM students");
while ($s = mysqli_fetch_assoc($r))
echo "<tr><td>$s[id]</td><td>$s[name]</td><td>$s[course]</td></tr>";
?>
</table>
