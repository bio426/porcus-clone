<template>
	<div class="Parallax" :class="background" ref="bg">
		<div class="Parallax__main">
			<div class="Parallax__container">
				<img class="Parallax__logo" src="../assets/images/logo.png" alt="" />
				<div v-if="page == 'index'">
					<h2 class="Parallax__title">Taberna Criolla</h2>
					<p class="Parallax__description">
						MARTES Y MIERCOLES:<br />
						Salón: De 08:30 a.m. a 04:00 p.m. <br />
						Rappi / Recojo en tienda: De 04:30 p.m. a 08:30 p.m. <br />
						<br />
						JUEVES / VIERNES / SABADO: De 08:30 a.m. a 11:00 p.m. <br />
						<br />
						DOMINGO: De 08:30 a.m. a 04:00 p.m.
					</p>
					<button class="Parallax__button">NUESTRA CARTA</button>
				</div>
				<div v-if="page == 'menu'">
					<h2 class="Parallax__title">NUESTRA CARTA</h2>
					<p class="Parallax__description">
						Contamos con una gran variedad de platos criollos que vas a poder
						disfrutar tanto que vas a volver. Desde nuestro famoso pan con
						chicharrón, pasando por un delicioso arroz con pato acompañado por
						una chicha porcus, hasta una torta de chocolate que está para
						repetir.
					</p>
				</div>
				<div v-if="page == 'promo'">
					<h2 class="Parallax__title">PROMOCIONES</h2>
					<p class="Parallax__description">
						Disfruta nuestras promociones en desayunos, para disfrutar
						acompañado, en familia o con amigos
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup lang="ts">
const props = defineProps({
	page: {
		type: String,
		required: true,
	},
})

let background = computed(() => {
	if (props.page == "index") return "Parallax--index"
	if (props.page == "menu") return "Parallax--menu"
	if (props.page == "promo") return "Parallax--promo"
	return ""
})

let bg = ref<HTMLDivElement>()
function handleSroll(e: Event) {
	bg.value.style.backgroundPositionY = window.scrollY * 0.7 + "px"
}

onMounted(() => window.addEventListener("scroll", handleSroll))
onBeforeUnmount(() => window.removeEventListener("scroll", handleSroll))
</script>

<style lang="scss">
.Parallax {
	position: relative;
	width: 100%;
	height: 100vh;
	background-image: linear-gradient(
		0deg,
		rgba(0, 0, 0, 0.4) 0%,
		rgba(0, 0, 0, 0.4) 100%
	);
	background-repeat: repeat;
	background-size: cover;
	background-position: 50% 50%;
	z-index: -1;

	&--index {
		background-image: linear-gradient(
				0deg,
				rgba(0, 0, 0, 0.4) 0%,
				rgba(0, 0, 0, 0.4) 100%
			),
			url("../assets/images/index-bg.jpg");
	}
	&--menu {
		background-image: linear-gradient(
				0deg,
				rgba(0, 0, 0, 0.4) 0%,
				rgba(0, 0, 0, 0.4) 100%
			),
			url("../assets/images/menu-bg.jpg");
	}
	&--promo {
		background-image: linear-gradient(
				0deg,
				rgba(0, 0, 0, 0.4) 0%,
				rgba(0, 0, 0, 0.4) 100%
			),
			url("../assets/images/promotions-bg.png");
	}

	&__main {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 100%;
		z-index: 10;
	}

	&__container {
		width: 60%;
	}

	&__logo {
		display: block;
		width: 100%;
		margin: 0 auto;
		margin-bottom: 1rem;

		@media (min-width: 768px) {
			width: 28rem;
		}
	}

	&__title {
		margin-bottom: 1rem;
		color: #fff;
		font-family: "Oswald";
		font-size: 2.5rem;
		font-weight: 500;
		text-align: center;
		text-transform: uppercase;
		letter-spacing: 2px;

		@media (min-width: 768px) {
			font-size: 3rem;
		}
	}

	&__description {
		color: #fff;
		margin-bottom: 1rem;
		text-align: center;
		font-size: 1rem;
		font-weight: 600;

		@media (min-width: 1024px) {
			font-size: 1.3rem;
		}
	}

	&__button {
		display: block;
		margin: 0 auto;
		padding: 0.5rem 0.8rem;
		background: #cca86a;
		border: none;
		border-radius: 1rem;
		outline: none;
		cursor: pointer;
		font-family: "Oswald";
		font-size: 1.5rem;
		letter-spacing: 2px;
		transition: all 0.5s ease;

		&:hover {
			letter-spacing: 3px;
			// background: darken($color: #CCA86A, $amount: 20%);
			opacity: 80%;
		}
	}
}
</style>
