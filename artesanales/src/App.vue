<template>
	
	<div class="">
		<nav class="navbar navbar-expand-lg navbar-light bg-light" style="background-color: #fff!important">
			<div class="container">
				<button class="navbar-toggler border-0" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar">
					<i class="bi bi-list"></i>
				</button>
				<a class="navbar-brand ms-2" href="#">Sist. Heladería</a>

				<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">
					<div class="offcanvas-header">
						<h5 class="offcanvas-title" id="offcanvasNavbarLabel">Menú</h5>
						<button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
					</div>
					<div class="offcanvas-body">
						<ul class="navbar-nav justify-content-end flex-grow-1 px-3">
							<li class="nav-item">
								<a class="nav-link d-flex align-items-center active" aria-current="page" href="#"><i class="bi bi-card-list"></i> <span>Carta</span></a>
							</li>
							<li class="nav-item">
								<a class="nav-link d-flex align-items-center" aria-current="page" href="#"><i class="bi bi-cart"></i> <span>Carrito</span></a>
							</li>
							<li class="nav-item">
								<a class="nav-link d-flex align-items-center" aria-current="page" href="#"><i class="bi bi-clipboard-check"></i> <span>Mis pedidos</span></a>
							</li>
							<li class="nav-item">
								<a class="nav-link d-flex align-items-center" aria-current="page" href="#"><i class="bi bi-joystick"></i> <span>Configuraciones</span></a>
							</li>
						</ul>
					</div>
				</div>
			</div>
		</nav>
		<section class="container">
			<div class="row my-3">
				<div class="col-9 position-relative">
					<div class="position-absolute ps-3 pt-2 top-0" id="divLupa" @click="siguiente()"><i class="bi bi-search"></i></div>
					<input type="text" id="txtBuscador" class="form-control" placeholder="¿Qué buscas?">
				</div>
				<div class="col d-flex justify-content-center">
					<button class="btn btn-warning rounded-pill d-block d-sm-none btnBuscar" id="">
						<i class="bi bi-arrow-right-circle"></i>
					</button>
					<button class="btn btn-warning rounded-pill d-none d-sm-block btnBuscar" id="">
						<i class="bi bi-arrow-right-circle"></i> Buscar
					</button>
				</div>
			</div>
		</section>
		<section class="container">
			<p class="mb-0" style="font-weight: 500;">Recomendados</p>
			
			<div class="swiper mySwiper">
	      <div class="swiper-wrapper">
	        <div class="swiper-slide"><img src="images/frap(1).jpg" alt=""></div>
	        <div class="swiper-slide"><img src="images/frap(2).jpg" alt=""></div>
	        <div class="swiper-slide"><img src="images/frap(3).jpg" alt=""></div>
	        <div class="swiper-slide"><img src="images/frap(4).jpg" alt=""></div>
	        <div class="swiper-slide"><img src="images/frap(5).jpg" alt=""></div>
	      </div>
      	<div class="swiper-pagination"></div>
	    </div>

		</section>
		<section class="container" id="contProductos">
			<p class="mb-0" style="font-weight: 500;">Podrías comprar</p>

			<div class="row">
				<div class="col-3"><img src="images/duvainilla.jpg"  class="rounded img-fluid"></div>
				<div class="col">
					<p class="titulo mb-2">Du Vainilla</p>
					<p class="descripcion">Vainilla y leche condensada</p>
				</div>
				<div class="col-3 dinero d-flex	align-items-center">S/ <span >8.40</span></div>
			</div>
			<div class="row">
				<div class="col-3"><img src="images/helados-frutales.jpg"  class="rounded img-fluid"></div>
				<div class="col">
					<p class="titulo mb-2">Mixto tropical</p>
					<p class="descripcion">Kiwi, Sandía y mango</p>
				</div>
				<div class="col-3 dinero d-flex	align-items-center">S/ <span >6.50</span></div>
			</div>
			<div class="row">
				<div class="col-3"><img src="images/helado-menta.jpg"  class="rounded img-fluid"></div>
				<div class="col">
					<p class="titulo mb-2">Refrescante Menta</p>
					<p class="descripcion">base de menta</p>
				</div>
				<div class="col-3 dinero d-flex	align-items-center">S/ <span >7.10</span></div>
			</div>

		</section>

		<!-- <router-view class="container" /> -->
	</div>
</template>

<script>
export default {
	name: 'App',
	components: {  },
	methods:{
		siguiente(){
			document.getElementById('txtBuscador').focus();
		}		
	},
	mounted(){
		var swiper = new Swiper(".mySwiper", {
				effect: "coverflow",
        grabCursor: true,
        centeredSlides: true,
        slidesPerView: "auto",
				loop: true,
        loopFillGroupWithBlank: true,
        coverflowEffect: {
          rotate: 50,
          stretch: 0,
          depth: 100,
          modifier: 1,
          slideShadows: true,
					
        },
        pagination: {
          el: ".swiper-pagination",
        },
      });
	}
	
}
</script>

<style>
*{font-family: 'Poppins', sans-serif;}

#nav a {
	font-weight: bold;
	color: #2c3e50;
}

#nav a.router-link-exact-active {
	color: #42b983;
}
.navbar>.container-fluid, .navbar>.container{
	justify-content: flex-start;
}
nav button:focus:not(:focus-visible){box-shadow: none;}
nav li {text-align: left!important;}
.nav-item, .nav-link>span{padding-left:1rem;}
.nav-item i{font-size: 1.5rem}
.nav-item .active{font-weight: 500;}
.navbar-toggler{font-size: 1.5rem;color: rgb(0 0 0);}
.navbar-light .navbar-brand{font-weight: 500;}
.bg-light{background-color: #fff;}
#txtBuscador::placeholder{font-size: 0.8rem; padding-left: 0.5rem;}
#txtBuscador{padding-left: 3rem;}
#divLupa{
	color:darkgray
}
.btnBuscar{
	background-color: #FF6B01;
	color:white;
}
.swiper {
  width: 100%;
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper-slide {
  background-position: center;
  background-size: cover;
  width: 300px;
  height: 300px;
}

.swiper-slide img {
  display: block;
  width: 100%;
}
.swiper-pagination-bullet-active{
	background: #ff6b01;
}
#contProductos .rounded {
    border-radius: 1rem!important;
}
.descripcion{
	margin-bottom: 0;
}
.titulo{
	font-weight: 500;
}
.descripcion{
	font-size: .8rem;
	color: #7a7a7a;
}
.dinero{
	font-size: 0.8rem;
}
.dinero>span{
	font-size: 1.8rem;
}
#contProductos .row{
	margin-bottom: 1rem;
}
</style>
