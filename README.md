# Easy-life-shopEasy-life-shop/
├── index.html
├── style.css
├── app.js
└── admin/
    ├── index.html
    ├── style.css
    └── admin.js
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Easy Life Shop</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

<header>
  <div class="wrap nav">

    <a class="brand" href="index.html">
      Easy<span>Life</span>
      <small>SHOP</small>
    </a>

    <nav>
      <a href="#shop">Boutique</a>
      <a href="#promos">Promotions</a>
      <a href="#categories">Catégories</a>
    </nav>

    <a class="cart" href="#cart">
      🛒 Panier <b id="cartCount">0</b>
    </a>

  </div>
</header>

<section class="hero">
  <div class="wrap">

    <div>
      <p class="tag">LA NOUVELLE FAÇON DE SHOPPER</p>

      <h1>
        Des produits tendance.
        <br>
        <em>Des prix qui comptent.</em>
      </h1>

      <p>
        Découvrez les nouveautés, promotions et meilleures ventes
        d’Easy Life Shop.
      </p>

      <a class="btn" href="#shop">
        Découvrir maintenant
      </a>
    </div>

    <div class="heroBox">
      <span>🔥 OFFRES FLASH</span>
      <strong>-30%</strong>
      <small>Sélection limitée</small>
    </div>

  </div>
</section>

<section id="categories" class="wrap section">

  <h2>Catégories</h2>

  <div id="cats" class="chips"></div>

</section>

<section id="promos" class="wrap section dark">

  <div>
    <span class="tag">🔥 PROMOTIONS</span>

    <h2>
      Les bonnes affaires du moment
    </h2>

    <p>
      Les prix promotionnels sont gérés depuis ton espace administrateur.
    </p>
  </div>

  <a class="btn light" href="#shop">
    Voir les offres
  </a>

</section>

<section id="shop" class="wrap section">

  <div class="head">

    <div>
      <span class="tag">NOTRE SÉLECTION</span>
      <h2>Produits</h2>
    </div>

    <input
      id="q"
      placeholder="🔎 Rechercher…"
      oninput="render()"
    >

  </div>

  <div id="products" class="grid"></div>

</section>

<section id="cart" class="wrap section cartBox">

  <h2>Ton panier</h2>

  <div id="cartItems"></div>

  <div class="total">
    Total :
    <b id="total">0 FCFA</b>
  </div>

  <button class="btn" onclick="checkout()">
    Commander
  </button>

</section>

<footer>

  <div class="wrap">

    <b>Easy Life Shop</b>

    <p>
      Mode • Beauté • Tendance • Côte d’Ivoire
    </p>

    <a href="admin/index.html">
      Administration
    </a>

  </div>

</footer>

<script src="app.js"></script>

</body>
</html>
:root{
  --a:#ff5b35;
  --dark:#101522;
  --bg:#f7f8fb;
  --muted:#687083;
  --line:#e6e8ee;
}

*{
  box-sizing:border-box;
}

html{
  scroll-behavior:smooth;
}

body{
  margin:0;
  font-family:Inter,system-ui,sans-serif;
  background:var(--bg);
  color:#111827;
}

a{
  text-decoration:none;
  color:inherit;
}

.wrap{
  width:min(1120px,92%);
  margin:auto;
}

header{
  background:#fff;
  border-bottom:1px solid var(--line);
  position:sticky;
  top:0;
  z-index:9;
}

.nav{
  height:70px;
  display:flex;
  align-items:center;
  gap:28px;
}

.brand{
  font-weight:950;
  font-size:21px;
}

.brand span{
  color:var(--a);
}

.brand small{
  display:block;
  font-size:7px;
  letter-spacing:3px;
  text-align:right;
  color:var(--muted);
}

nav{
  display:flex;
  gap:22px;
  flex:1;
  color:#4b5563;
}

.cart{
  border:1px solid var(--line);
  padding:9px 12px;
  border-radius:10px;
}

.cart b{
  background:var(--a);
  color:white;
  border-radius:50%;
  padding:2px 7px;
}

.hero{
  background:linear-gradient(135deg,#fff,#fff0eb);
  padding:75px 0;
}

.hero .wrap{
  display:grid;
  grid-template-columns:1.4fr .6fr;
  gap:45px;
  align-items:center;
}

.tag{
  font-weight:900;
  color:var(--a);
  font-size:12px;
  letter-spacing:1.2px;
}

.hero h1{
  font-size:clamp(42px,7vw,76px);
  line-height:.98;
  margin:14px 0;
}

.hero em{
  color:var(--a);
  font-style:normal;
}

.hero p{
  font-size:18px;
  color:var(--muted);
  line-height:1.6;
  max-width:620px;
}

.btn{
  display:inline-block;
  background:var(--a);
  color:white;
  border:0;
  border-radius:12px;
  padding:13px 18px;
  font-weight:850;
  cursor:pointer;
}

.hero .btn{
  margin-top:15px;
}

.heroBox{
  background:var(--dark);
  color:white;
  border-radius:28px;
  padding:50px 30px;
  text-align:center;
  box-shadow:0 25px 60px #0002;
}

.heroBox span{
  color:#ff9d61;
  font-weight:900;
}

.heroBox strong{
  display:block;
  font-size:65px;
  margin:10px;
}

.heroBox small{
  color:#cbd5e1;
}

.section{
  padding:55px 0;
}

.section h2{
  font-size:30px;
  margin:8px 0 20px;
}

.chips{
  display:flex;
  gap:10px;
  flex-wrap:wrap;
}

.chips button{
  background:#fff;
  border:1px solid var(--line);
  padding:11px 17px;
  border-radius:999px;
  cursor:pointer;
}

.dark{
  background:var(--dark);
  color:white;
  border-radius:25px;
  padding:38px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.dark p{
  color:#cbd5e1;
}

.light{
  background:white;
  color:#111827;
}

.head{
  display:flex;
  justify-content:space-between;
  align-items:end;
  gap:15px;
}

.head input{
  padding:13px;
  border:1px solid var(--line);
  border-radius:10px;
  width:280px;
  font:inherit;
}

.grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:18px;
}

.card{
  background:white;
  border:1px solid var(--line);
  border-radius:17px;
  overflow:hidden;
}

.card img{
  width:100%;
  aspect-ratio:1;
  object-fit:cover;
  background:#eee;
}

.cardBody{
  padding:15px;
}

.badge{
  font-size:11px;
  font-weight:850;
  color:var(--a);
  background:#fff0eb;
  padding:5px 8px;
  border-radius:7px;
}

.card h3{
  margin:10px 0 6px;
}

.desc{
  font-size:13px;
  color:var(--muted);
  min-height:38px;
}

.price{
  font-weight:900;
  font-size:19px;
  margin-top:10px;
}

.old{
  text-decoration:line-through;
  color:#9ca3af;
  font-size:13px;
  margin-left:5px;
}

.card .btn{
  width:100%;
  margin-top:12px;
}

.empty{
  grid-column:1/-1;
  text-align:center;
  color:var(--muted);
  padding:35px;
}

.cartBox{
  background:#fff;
  padding:30px;
  border-radius:20px;
}

.cartLine{
  display:flex;
  justify-content:space-between;
  padding:13px 0;
  border-bottom:1px solid var(--line);
}

.total{
  text-align:right;
  font-size:21px;
  padding:20px 0;
}

footer{
  background:var(--dark);
  color:white;
  padding:40px 0;
}

footer p{
  color:#cbd5e1;
}

footer a{
  color:#ff9d61;
}

@media(max-width:800px){

  nav{
    display:none;
  }

  .hero .wrap{
    grid-template-columns:1fr;
  }

  .grid{
    grid-template-columns:repeat(2,1fr);
  }

  .dark{
    display:block;
  }

  .head{
    align-items:stretch;
    flex-direction:column;
  }

  .head input{
    width:100%;
  }

}

@media(max-width:480px){

  .grid{
    grid-template-columns:1fr;
  }

  .hero{
    padding:50px 0;
  }

}
const fallback = [

  {
    id:1,
    name:"Chemise tendance",
    cat:"Mode",
    price:4000,
    promo:3500,
    desc:"Élégante, confortable et facile à porter.",
    img:"https://images.unsplash.com/photo-1603252110481-7ba873bf42ab?auto=format&fit=crop&w=700&q=80"
  },

  {
    id:2,
    name:"Sélection beauté",
    cat:"Beauté",
    price:8000,
    promo:6500,
    desc:"Une sélection beauté à découvrir.",
    img:"https://images.unsplash.com/photo-1598440947619-2c35fc9aa908?auto=format&fit=crop&w=700&q=80"
  },

  {
    id:3,
    name:"Article tendance",
    cat:"Tendance",
    price:10000,
    promo:0,
    desc:"Nouveau produit de la boutique.",
    img:"https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=700&q=80"
  }

];

let products =
  JSON.parse(localStorage.getItem("els_products") || "null")
  || fallback;

let cart =
  JSON.parse(localStorage.getItem("els_cart") || "[]");

let cat = "Tous";

const money = n =>
  Number(n).toLocaleString("fr-FR") + " FCFA";


function renderCats(){

  let cats = [
    "Tous",
    ...new Set(products.map(p => p.cat))
  ];

  document.querySelector("#cats").innerHTML =
    cats.map(c =>
      `<button onclick="cat='${c}';render()">
        ${c}
      </button>`
    ).join("");

}


function render(){

  renderCats();

  let q =
    (document.querySelector("#q").value || "")
    .toLowerCase();

  let list = products.filter(p =>

    (cat === "Tous" || p.cat === cat)

    &&

    (p.name + " " + p.desc)
      .toLowerCase()
      .includes(q)

  );


  document.querySelector("#products").innerHTML =

    list.length

    ?

    list.map(p => `

      <article class="card">

        <img
          src="${p.img || 'https://placehold.co/700?text=Easy+Life'}"
          alt=""
        >

        <div class="cardBody">

          <span class="badge">
            ${p.cat}
          </span>

          <h3>
            ${p.name}
          </h3>

          <div class="desc">
            ${p.desc || ""}
          </div>

          <div class="price">

            ${money(p.promo || p.price)}

            ${
              p.promo
              ?
              `<span class="old">
                ${money(p.price)}
              </span>`
              :
              ""
            }

          </div>

          <button
            class="btn"
            onclick="add(${p.id})"
          >
            Ajouter au panier
          </button>

        </div>

      </article>

    `).join("")

    :

    `<div class="empty">
      Aucun produit trouvé.
    </div>`;

  renderCart();

}


function add(id){

  let x = cart.find(x => x.id === id);

  if(x){

    x.qty++;

  }else{

    cart.push({
      id,
      qty:1
    });

  }

  localStorage.setItem(
    "els_cart",
    JSON.stringify(cart)
  );

  renderCart();

  location.hash = "cart";

}


function renderCart(){

  document.querySelector("#cartCount")
    .textContent =
      cart.reduce(
        (s,x) => s + x.qty,
        0
      );


  let el =
    document.querySelector("#cartItems");

  let total = 0;


  el.innerHTML = cart.length

    ?

    cart.map(x => {

      let p =
        products.find(y => y.id === x.id);

      let price =
        p.promo || p.price;

      total += price * x.qty;

      return `

        <div class="cartLine">

          <span>
            ${p.name} × ${x.qty}
          </span>

          <b>
            ${money(price * x.qty)}
          </b>

        </div>

      `;

    }).join("")

    :

    "<p>Ton panier est vide.</p>";


  document.querySelector("#total")
    .textContent =
      money(total);

}


function checkout(){

  if(!cart.length){

    alert("Ton panier est vide.");

    return;

  }

  alert(
    "Prochaine étape : connecter la commande au paiement et à la livraison."
  );

}


render();

admin
Easy-life-shop/
│
├── index.html
├── style.css
├── app.js
│
└── admin/
    ├── index.html
    ├── style.css
    └── admin.js
https://easylifeshop011-netizen.github.io/Easy-life-shop/admin/