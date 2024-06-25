# Project-1

Font Awasome 
===
    <!-- Font Awasome -->
    <script src="https://kit.fontawesome.com/1d23864fb5.js" crossorigin="anonymous"></script>

Google Fonts 
===
   <!-- Google - Font -->
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat&display=swap" rel="stylesheet">
===
Bootstap (v5.3)
   <!--Bootstrap CSS  -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">

       <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
        crossorigin="anonymous"></script> 
---

---
Navbar
https://getbootstrap.com/docs/5.3/components/navbar/
+     position-sticky top-0
+     navbar-nav ms-auto
-     fluid
-     bg-body-tertiary
-                    <li class="nav-item">
                        <a class="nav-link disabled" aria-disabled="true">Disabled</a>
                    </li>
---
⚠️ w Bootstrapie każdy paragraf ma ustawiony automatycznie margines od dołu i trzeba go ręcznie zmieniać ⚠️  🔷 mb-1 🔷

===
HTML (index.html)
---
https://fontawesome.com/icons/bars?f=classic&s=solid
-     <span class="navbar-toggler-icon"></span>
+     <i class="fa-solid fa-bars"></i>
+     <i class="fa-solid fa-headset"></i>
-     Navbar - zaminana nazwy na ikonę i dodaję nazwę PROGAMERS

+  dodanie dodatkowych nav-link (o nas; portfolio; cena; zespół; osiągnięcia; kontakt)

---

===
CSS(Scss) (main.scss)(_colors.scss)
---
+                     nav {
                            text-transform : uppercase;
                       .nav-link, .navbar-nav .nav-link.active, .navbar-nav .show>.nav-link, .navbar-brand, .fa-bars {
                            color: #fff;
                    
+                        .nav-link:focus, .nav-link:hover, .navbar-nav .nav-link.active, .navbar-nav .show>.nav-link {
                         color: #039dff;
                         z-index:5;       #Zapobiega przykrywaniu nawigacji
                        }
                    }
_colors.scss
+         $main-color: #039dff;
          $white-color: #fff;
          $light-grey;

main.scss
---
+      @use './colors' as *;
         color: $white-color;
          color: $main-color;
---
HEADER
---
+    header.hero-img {
+       position:relative;
        height:100vh;
        backgroung-image: url("../img/hero-small.jpeg");
        background-size: cover;
         background-position: center;

 ❗❗ Problemy ze wsparciem np: Safarii ❗❗
+        background-attachment: fixed;
  
+         color: $white;
        z-index: 0;    #CIEŃ(1)
         h1 {
             text-transform: uppercase;
         }
      }

+    .hero-shadow {
+       position: absolute;
       top: 0;
       left: 0;
       width: 100%;
       height: 100%;
        background-color: rgb(0,0,0,.8);
        z-index: -5;   #CIEŃ(1)
        }
WYŚRODKOWANIE TEKSTU NA STRONIE (domyślnie jest flex-direction row ⚠️)
+    .hero-text {
+       display: flex;
        justyfy-content: center;
        align-items: center;
        flex-direction: column    #Trzeba dodać by wyśrodkować tekst
         height: 100%;
       }
ZAMIANA KOLORU GAMERS
+        .blue-text {
        color: $main.color;
       }

===
JS (script.js)
---
+     dodaje do index.html 🔶 <script src="./js/script.js"></script> 🔶
+     Zamiast 'click' daję DOMContentLoader'    🔶 document.addEventListener('DOMContentLoaded', function () {🔶
+    	  trzyma moją nawigację        🔶    const nav = document.querySelector('.navbar') 🔶
scss
+     dodaję .shadow-bg {
    	background-color: rgba(0,0,0,.9);
        }
===
MOBILE - CORECT 📱 = iPhone 5/SE ✅ Samsung Galaxy S8+✅ iPadPro✅ Samsung Galaxy S20 Ultra✅
===
HTML
....
+      dodaję text-center    <div class="hero-text text-center">  🔶 Lub w SCSS dodaje text-align: center   wyjdzie na to samo 🔶 
+     dodaję padding 2 kategorii  🔶  <div class="hero-text text-center p-2">
SCSS
....
+     @media (min-width: 768px) {
	    .hero-text {
		    h1 {
			    font-size: 42px;
		    }
		
		p{
			font-size: 20px;
		}
MAIN index.html
....
+     id = lepiej jest używać w JS lub do kotwiczenia elementów na stronie niż stylowaniu CSS 🔴 id zjada pamięć 🔴

+     Dodajemy class i podpinamy z id na 🔶  <section id="aboutus" class="aboutus bg-light py-5 ">
+     pozycjonowanie kontenera na stronie   🔶   <div class="container">
+      <h2 class="section-title">o nas</h2>
+      <div class="underline"></div>
+         🔵 <div class="row"> 🔵
+            🔵 <div class="col-sm-6 col-md-4 text-center"> 🔵
  ikony z Font Awesome
+        <p><i class="fa-solid fa-mobile-screen"></i></p>
+        <p><i class="fas fa-desktop"></i></p>
+        <p><i class="fas fa-file-code"></i></p>
+        <p><i class="fas fa-paw"></i></p>
+         <p><i class="fas fa-hamburger"></i></p>
+          <p><i class="fas fa-glass-cheers"></i></p>
Scss
+    POWIĘKSZENIE TEKSTU I WYŚRODKOWANIE
+        .section-title {
	    text-align: center;
    	text-transform: uppercase;
        }
+    KRESKA POD NAPISEM
+        .underline {
+     	W elemencie blokowym  🔶 margin: 0 auto 40px;🔶
	    width: 60px;
	    height: 4px;
	    background-color: $main-color;
        }
+		.aboutus {
		i {
		margin-top: 20px;
		font-size: 30px;
		}

+		.aboutus-card-title {
			font-size: 18px;
			text-transform: uppercase;
		}

+		.aboutus-card-text {
			font-size: 14px;
		}
		}
ABOUT - PODŚWIETLENIE IKON NA BŁĘKITNY 🔵 :hover 🔵
+		 <div class="col-sm-6 col-md-4 text-center 🔹 aboutus-hover🔹">
		 
+		.aboutus-hover{
			transition: color .3s;
			}
+		 .aboutus-hover:hover {
		color: $main-color;
		
			}
PRZYDATNA WŁĄŚCIWOŚĆ DO SCROLOWANIA NA TELEFONY ✳️

+ SCSS
+	dodajemy
+		html {
		scroll-padding-top: 74px ;
		}
⚠️ F12 - po najechaniu na pasek nawigacji widzę jakie parametry i jaki styl ma pasek w tym wypadku 74px ⚠️

PRZYDATNA WŁĄŚCIWOŚĆ DO SCROLOWANIA NA PC ✳️
+		 @media (min-width: 992px){
			html {
			scroll-padding-top: 72px ;
			}
		}
ZAMYKANIE NAWIGACJI PO NACIŚNIĘCIU WYBORU LUB INNEGO MIEJSCA NA TELEGONIE ✴️ JS ✴️
AUTOMATYCZNE ZAMYKANIE...
+ Badam nawigację w F12
+ 		dodaję do js. wszystkie linki ✴️	const allNavItems = document.querySelectorAll('.nav-link')
+ 		trzeba dodać by show się aktywowało ✴️ const navList = document.querySelector('.navbar-collapsa')
+ 		dodaję nasłuchiwanie na clicka w pętli na wszystkie linki ✴️
+ 		allNavItems.forEach(item => item.addEventListener('click', () => {navList.classList.remove('show')	
		}))
❇️ SEKCJA - TWORZYMY GRY NA PLATFORMY ❇️ HTML
+ 		 <section class="aboutus-hero py-5">
         	   <div class="aboutus-shadow"></div>

          	  <div class="cointener"></div>
          	      <h2  class="section-title">tworzymy gry na platformy</h2>
	                <div class="underline"></div>
     		   </section>
❇️ SEKCJA - TWORZYMY GRY NA PLATFORMY ❇️ SCSS 
+		.aboutus-hero {
		position: relative;
		background-image: url(../img/pc-small.jpg);
		background-size: cover;
		background-position: center;
		color: $light-grey;
		z-index: 0;
+		.aboutus-shadow {
  		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.7);
		z-index: -5;
		}
             } 
