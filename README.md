<!DOCTYPE html>
<html lang="en">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>PrimeStrength Ultra</title>

<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;500;700&display=swap" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Montserrat', sans-serif;
}

body{
background:#000;
color:#fff;
}

/* HEADER */
header{
display:flex;
justify-content:space-between;
align-items:center;
padding:20px;
border-bottom:1px solid gold;
position:sticky;
top:0;
background:#000;
}

.logo{
color:gold;
font-size:24px;
font-weight:700;
}

#search{
padding:10px;
border:none;
border-radius:6px;
outline:none;
}

/* MENU */
nav{
display:flex;
flex-wrap:wrap;
gap:10px;
justify-content:center;
padding:20px;
}

nav button{
background:#111;
border:1px solid gold;
color:white;
padding:10px;
cursor:pointer;
transition:.3s;
}

nav button:hover{
background:gold;
color:#000;
}

/* PRODUCTS */
.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:20px;
padding:20px;
}

.card{
background:#111;
padding:15px;
border-radius:10px;
border:1px solid #222;
transition:.3s;
}

.card:hover{
transform:scale(1.03);
border-color:gold;
}

.card h3{
color:gold;
margin-bottom:5px;
}

.card p{
opacity:0.8;
margin-bottom:10px;
}

.card button{
background:gold;
border:none;
padding:8px 12px;
cursor:pointer;
font-weight:bold;
}

/* FOOTER */
footer{
text-align:center;
padding:40px;
border-top:1px solid gold;
margin-top:20px;
}

a{
color:gold;
text-decoration:none;
}

</style>
</head>

<body>

<header>
<div class="logo">PRIMESTRENGTH</div>
<input id="search" placeholder="Search..." onkeyup="search()">
</header>

<nav id="menu"></nav>

<section class="products" id="products"></section>

<footer>

<h3>PrimeStrength Store</h3>

<!-- WhatsApp بزنس مضبوط -->
<a href="https://wa.me/9617606292?text=Hello%20I%20want%20to%20order" target="_blank">
Contact on WhatsApp
</a>

<p>Phone: 76062928</p>

</footer>

<script>

const categories=[
"MMA","Boxing","Swimming","Massage","Hiking","Fitness",
"Running","Yoga","Cycling","Climbing","Football",
"Basketball","Tennis","Crossfit","Recovery"
];

const menu=document.getElementById("menu");
const products=document.getElementById("products");

/* build menu */
categories.forEach(c=>{
let b=document.createElement("button");
b.innerText=c;
b.onclick=()=>load(c);
menu.appendChild(b);
});

/* products */
function load(cat){

products.innerHTML="";

for(let i=1;i<=6;i++){

products.innerHTML+=`
<div class="card">
<h3>${cat} Gear ${i}</h3>
<p>Professional Equipment</p>
<p>${(10+i)*3}$</p>

<button onclick="order('${cat} Gear ${i}')">
Order Now
</button>

</div>
`;

}

}

/* FIXED WHATSAPP (IMPORTANT 🔥) */
function order(item){

let phone="9617606292";
let msg="Hello I want "+item;

let url="https://wa.me/"+phone+"?text="+encodeURIComponent(msg);

window.open(url,"_blank");

}

/* search */
function search(){

let v=document.getElementById("search").value.toLowerCase();

document.querySelectorAll(".card").forEach(c=>{
c.style.display=
c.innerText.toLowerCase().includes(v)
?"block":"none";
});

}

/* default */
load("Boxing");

</script>

</body>
</html>
