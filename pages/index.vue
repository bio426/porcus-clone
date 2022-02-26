<template>
	<div class="index">
		<Header />
		<Parallax page="index" />
		<div class="index__sec1">
			<div>
				<h4 class="index__subtitle">Lo que servimos</h4>
				<h2 class="index__title">Nuestra carta</h2>
			</div>
			<p class="index__description">
				Contamos con una gran variedad de platos criollos que vas a poder
				disfrutar tanto que vas a volver. Desde nuestro famoso pan con
				chicharrón, pasando por un delicioso arroz con pato acompañado por una
				chicha porcus, hasta una torta de chocolate que está para repetir.
			</p>
		</div>
		<div class="index__sec2">
			<div class="ICard">
				<img class="ICard__image" src="../assets/images/icard1.jpg" alt="" />
				<h4 class="ICard__title">Desayunos & Brunch</h4>
				<p class="ICard__description">
					Perfectos para la mañana, el mediodía o el lonche, tenemos una variada
					carta de sánguches y piqueos para compartir, para que los disfrutes en
					cualquier momento del día.
				</p>
			</div>
			<div class="ICard">
				<img class="ICard__image" src="../assets/images/icard2.jpg" alt="" />
				<h4 class="ICard__title">Nuestros Fondos</h4>
				<p class="ICard__description">
					Lo mejor de nuestra carta está aquí, una selección de deliciosos
					platos criollos, preparados con la mejor selección de ingredientes y
					sobre todo con mucho corazón.
				</p>
			</div>
			<div class="ICard">
				<img class="ICard__image" src="../assets/images/icard3.jpg" alt="" />
				<h4 class="ICard__title">La barra de Porcus</h4>
				<p class="ICard__description">
					Para el fin de semana o un after office, nuestra gran carta de
					cocteles te va a encantar. No vas a poder pedir solo uno. ¡Salud!
				</p>
			</div>

			<div class="ICard">
				<img class="ICard__image" src="../assets/images/icard4.jpg" alt="" />
				<h4 class="ICard__title">Empacados al vacío</h4>
				<p class="ICard__description">
					Prende la parrilla, calienta el horno o saca el sartén y llévalo
					directo al fuego, porque nosotros nos encargamos del resto. Disfruta
					nuestros productos empacados al vacío en cualquier lugar.
				</p>
			</div>
		</div>
		<button class="index__button">Nuestra carta</button>
		<div class="index__sec3">
			<img class="index__image" src="../assets/images/local1.jpg" alt="" />
			<img class="index__image" src="../assets/images/local2.jpg" alt="" />
			<img class="index__image" src="../assets/images/local3.jpg" alt="" />
		</div>
		<div class="index__sec4">
			<h2 class="index__promo">Promociones</h2>
			<p class="index__promoDesc">
				Disfruta nuestras promociones en desayunos, para disfrutar acompañado,
				en familia o con amigos
			</p>
			<div class="index__promoCards">
				<div class="ICard">
					<img class="ICard__image" src="../assets/images/promo1.png" alt="" />
					<h4 class="ICard__title">Desayuno Porcus</h4>
					<p class="ICard__description">S/ 95.00</p>
				</div>
				<div class="ICard">
					<img class="ICard__image" src="../assets/images/promo2.png" alt="" />
					<h4 class="ICard__title">Desayuno Peruano</h4>
					<p class="ICard__description">S/ 193.00</p>
				</div>
			</div>
		</div>
		<button class="index__button">Mas promociones</button>
		<div class="Booking">
			<div class="Booking__container">
				<h4 class="Booking__title">Reserva</h4>
				<p class="Booking__description">
					Te esperamos para que disfrutes lo mejor de nuestra carta. No olvides
					que por la coyuntura actual nuestro aforo es reducido, por eso te
					recomendamos realizar tu reserva antes.
				</p>
				<div class="Booking__fields">
					<input class="Booking__input" type="text" placeholder="Nombre" />
					<input class="Booking__input" type="text" placeholder="Teléfono" />
					<input
						class="Booking__input"
						type="text"
						placeholder="Dirección de correo electrónico"
					/>
					<select class="Booking__input" name="" id="">
						<option value="" selected>Cantidad de personas</option>
						<option value="">opt1</option>
						<option value="">opt2</option>
					</select>
					<input
						class="Booking__input Booking__input--span2"
						type="text"
						placeholder="Fecha y hora de reserva"
					/>
					<textarea
						class="Booking__input Booking__input--span2"
						cols="30"
						rows="5"
						placeholder="Mensaje"
					></textarea>
					<div class="Booking__span2">
						<button class="Booking__send">Enviar</button>
					</div>
				</div>
			</div>
		</div>
		<img class="index__map" src="../assets/images/imap.png" alt="" />
		<Footer />
		<FloatAction />
	</div>
</template>

<style lang="scss">
.index {
	position: relative;
	display: block;
	width: 100%;
	min-height: 100vh;

	&__sec1 {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		gap: 4rem;
		width: 80%;
		margin: 5rem auto;
	}

	&__subtitle {
		display: block;
		color: #cca86a;
		font-size: 1.4rem;
		font-weight: 600;
	}
	&__title {
		display: block;
		color: #333333;
		font-family: "Oswald";
		font-size: 3.5rem;
		font-weight: 600;
		letter-spacing: 4px;
		line-height: 1.2;
		text-transform: uppercase;
	}
	&__description {
		color: #666666;
		font-size: 1.2rem;
		font-weight: 600;
	}

	&__sec2 {
		display: grid;
		grid-template-columns: 1fr;
		gap: 2rem;
		width: 80%;
		margin: 0 auto;

		@media (min-width: 768px) {
			grid-template-columns: 1fr 1fr;
		}

		@media (min-width: 1024px) {
			grid-template-columns: repeat(4, 1fr);
		}
	}

	&__button {
		display: block;
		margin: 4rem auto;
		padding: 0.5rem 0.8rem;
		background: #cca86a;
		border: none;
		border-radius: 1rem;
		outline: none;
		cursor: pointer;
		font-family: "Oswald";
		font-size: 1.4rem;
		font-weight: 500;
		letter-spacing: 1px;
		text-transform: uppercase;
		transition: all 0.5s ease;

		&:hover {
			letter-spacing: 2px;
			background: lighten($color: #cca86a, $amount: 10%);
		}
	}

	&__sec3 {
		display: grid;
		grid-template-columns: 1fr;
		width: 100%;
		margin-bottom: 6rem;

		@media (min-width: 1024px) {
			grid-template-columns: repeat(3, 1fr);
		}
	}

	&__image {
		display: block;
		width: 100%;
	}

	&__sec4 {
		width: 80%;
		margin: 0 auto;
	}

	&__promo {
		display: block;
		margin-bottom: 2rem;
		color: #333333;
		font-family: "Oswald";
		font-size: 2.5rem;
		font-weight: 600;
		letter-spacing: 4px;
		text-transform: uppercase;
		text-align: center;

		@media (min-width: 768px) {
			font-size: 3rem;
		}
	}

	&__promoDesc {
		display: block;
		margin-bottom: 4rem;
		color: #666666;
		text-align: center;
		font-size: 1.2rem;
		font-weight: 600;
	}

	&__promoCards {
		display: grid;
		grid-template-columns: 1fr;
		gap: 4rem;
		margin: 0 auto;

		@media (min-width: 768px) {
			width: 50%;
		}

		@media (min-width: 1024px) {
			width: 100%;
			grid-template-columns: 1fr 1fr;
		}
	}

	&__map {
		display: block;
		width: 100%;
		height: 40rem;
		object-fit: cover;
	}
}

.ICard {
	padding: 1.5rem;
	border: 1px solid rgba($color: #000000, $alpha: 0.2);
	transition: all 0.5s ease;

	@media (min-width: 1024px) {
		min-width: 9rem;
	}

	&:hover {
		box-shadow: 0px 0px 60px 0px rgba(0, 0, 0, 0.2);
	}

	&__image {
		display: block;
		width: 100%;
		margin-bottom: 2rem;
	}

	&__title {
		margin-bottom: 1rem;
		color: #333333;
		font-family: "Oswald";
		font-size: 2rem;
		letter-spacing: 3px;
		text-align: center;
	}

	&__description {
		color: #666666;
		text-align: center;
	}
}

.Booking {
	width: 100%;
	padding: 5rem 0;
	background-image: linear-gradient(
			272deg,
			rgba(0, 0, 0, 0.4) 0%,
			rgba(0, 0, 0, 0.4) 100%
		),
		url("../assets/images/booking-bg.png");
	background-size: cover;
	background-repeat: no-repeat;

	&__container {
		width: 80%;
		margin: 0 auto;

		@media (min-width: 1024px) {
			width: 60%;
			margin: 0;
			margin-left: 10%;
		}
	}

	&__title {
		display: block;
		margin-bottom: 2rem;
		color: #fff;
		font-family: "Oswald";
		font-size: 3.5rem;
		font-weight: 600;
		letter-spacing: 4px;
		line-height: 1.2;
		text-align: center;
		text-transform: uppercase;
	}

	&__description {
		margin-bottom: 2rem;
		color: #fff;
		font-size: 1.2rem;
		font-weight: 600;
	}

	&__fields {
		display: grid;
		grid-template-columns: 1fr;
		gap: 1rem;

		@media (min-width: 768px) {
			grid-template-columns: 1fr 1fr;
		}
	}

	&__input {
		display: block;
		padding: 1rem;
		background: #fff;
		color: #333333;
		border: none;
		border-radius: 1rem;
		outline: none;

		@media (min-width: 768px) {
			&--span2 {
				grid-column: span 2;
			}
		}
	}

	@media (min-width: 768px) {
		&__span2 {
			grid-column: span 2;
		}
	}

	&__send {
		display: inline;
		float: right;
		padding: 0.5rem 0.8rem;
		background: #cca86a;
		border: none;
		border-radius: 1rem;
		outline: none;
		cursor: pointer;
		font-family: "Oswald";
		font-size: 1.4rem;
		font-weight: 500;
		letter-spacing: 1px;
		text-transform: uppercase;
		transition: all 0.5s ease;

		&:hover {
			letter-spacing: 2px;
			background: lighten($color: #cca86a, $amount: 10%);
		}
	}
}
</style>
