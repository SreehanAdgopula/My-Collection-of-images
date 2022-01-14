
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
   
<style>
* {
  box-sizing: border-box;
}

body {
  background-color: #f1f1f1;
  padding: 20px;
  font-family: Arial;
}

/* Center website */
.main {
  max-width: 1000px;
  margin: auto;
}

h1 {
  font-size: 50px;
  word-break: break-all;
}

.row {
  margin: 10px -16px;
}

/* Add padding BETWEEN each column */
.row,
.row > .column {
  padding: 8px;
}

/* Create three equal columns that floats next to each other */
.column {
  float: left;
  width: 33.33%;
  display: none; /* Hide all elements by default */
}

/* Clear floats after rows */ 
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Content */
.content {
  background-color: white;
  padding: 10px;
}

/* The "show" class is added to the filtered elements */
.show {
  display: block;
}

/* Style the buttons */
.btn {
  border: none;
  outline: none;
  padding: 12px 16px;
  background-color: white;
  cursor: pointer;
}

.btn:hover {
  background-color: #ddd;
}

.btn.active {
  background-color: #666;
  color: white;
}
</style>
</head>
<body>

<!-- MAIN (Center website) -->
<div class="main">

<h1 class="glow">My Collection of images</h1>
<hr>

<h2 class="glow">Images</h2>

<div id="myBtnContainer">
  <button class="btn active" onclick="filterSelection('all')"> Show all</button>
  <button class="btn" onclick="filterSelection('Space')"> Space</button>
  <button class="btn" onclick="filterSelection('Painting')"> Painting</button>
  <button class="btn" onclick="filterSelection('Minecraft')"> Minecraft</button>
  <button class="btn" onclick="filterSelection('Colorful')"> Colorful</button>
  <button class="btn" onclick="filterSelection('Special')"> Special</button>
</div>

<!-- Portfolio Gallery Grid -->
<div class="row">
  <div class="column Space">
    <div class="content">
      <img src="space.jpeg" alt="Space" style="width:100%">
      <h4></h4>
      <p></p>
    </div>
  </div>
  <div class="column Space">
    <div class="content">
    <img src="bg-04.jpg" alt="Space" style="width:100%">
     </div>
  </div>
  <div class="column Space">
    <div class="content">
    <img src="OIP (1).jpeg" alt="Space" style="width:100%">
      
    </div>
  </div>
  
  <div class="column Painting">
    <div class="content">
      <img src="SAAHITYA GIFT CARD.png" alt="Painting" style="width:100%">
      
    </div>
  </div>
  <div class="column Painting">
    <div class="content">
    <img src="name.jpg" alt="Painting" style="width:100%">
      
    </div>
  </div>
  <div class="column Painting">
    <div class="content">
    <img src="favicon.jpg" alt="Painting" style="width:100%">
      
    </div>
  </div>

  <div class="column Minecraft">
    <div class="content">
      <img src="OIP (1).jpg" alt="Minecraft" style="width:100%">
      
    </div>
  </div>
  <div class="column Minecraft">
    <div class="content">
    <img src="ok.jpg" alt="Minecraft" style="width:100%">
      
    </div>
  </div>
  <div class="column Minecraft">
    <div class="content">
    <img src="image.jpg" alt="Minecraft" style="width:100%">
     
    </div>
  </div>
  
  
  <div class="column Colorful">
    <div class="content">
      <img src="color.jpg" alt="Colorful" style="width:100%">
      <h4></h4>
      <p></p>
    </div>
  </div>
  
  
  <div class="column Colorful">
    <div class="content">
      <img src="index.jpg" alt="Colorful" style="width:100%">
      <h4></h4>
      <p></p>
    </div>
  </div>
  
 
  <div class="column Colorful">
    <div class="content">
      <img src="images.jfif" alt="Colorful" style="width:100%">
      <h4></h4>
      <p></p>
    </div>
  </div>
 
 <div class="column Special">
 <h3>Coming soon!</h3>
     <center> <svg height="200" width="500">
  <defs>
    <linearGradient id="grad1" x1="10%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%"
      style="stop-color:rgb(255,255,0);stop-opacity:1" />
      <stop offset="100%"
      style="stop-color:rgb(255,0,0);stop-opacity:1" />
    </linearGradient>
  </defs>
  <ellipse cx="100" cy="70" rx="85" ry="55" fill="url(#grad1)" />
  <text fill="#0000ff" font-size="35" font-family="Verdana"
  x="50" y="80">THANK YOU</text>
</svg> </center>
  
 
<!-- END GRID -->
</div>

<!-- END MAIN -->
</div>

<script>
filterSelection("all")
function filterSelection(c) {
  var x, i;
  x = document.getElementsByClassName("column");
  if (c == "all") c = "";
  for (i = 0; i < x.length; i++) {
    w3RemoveClass(x[i], "show");
    if (x[i].className.indexOf(c) > -1) w3AddClass(x[i], "show");
  }
}

function w3AddClass(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    if (arr1.indexOf(arr2[i]) == -1) {element.className += " " + arr2[i];}
  }
}

function w3RemoveClass(element, name) {
  var i, arr1, arr2;
  arr1 = element.className.split(" ");
  arr2 = name.split(" ");
  for (i = 0; i < arr2.length; i++) {
    while (arr1.indexOf(arr2[i]) > -1) {
      arr1.splice(arr1.indexOf(arr2[i]), 1);     
    }
  }
  element.className = arr1.join(" ");
}


// Add active class to the current button (highlight it)
var btnContainer = document.getElementById("myBtnContainer");
var btns = btnContainer.getElementsByClassName("btn");
for (var i = 0; i < btns.length; i++) {
  btns[i].addEventListener("click", function(){
    var current = document.getElementsByClassName("active");
    current[0].className = current[0].className.replace(" active", "");
    this.className += " active";
  });
}
</script>
    <script>
// Get the modal
var modal = document.getElementById("myModal");

// Get the image and insert it inside the modal - use its "alt" text as a caption
var img = document.getElementById("myImg");
var modalImg = document.getElementById("img01");
var captionText = document.getElementById("caption");
img.onclick = function(){
  modal.style.display = "block";
  modalImg.src = this.src;
  captionText.innerHTML = this.alt;
}

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// When the user clicks on <span> (x), close the modal
span.onclick = function() { 
  modal.style.display = "none";
}
</script>
