<template>
	<div class="promo">
		<Header />
		<Parallax page="promo" />
		<div class="promo__sec">
			<div class="Card">
				<img class="Card__image" src="../assets/images/promo1.png" alt="" />
				<h4 class="Card__title">Desayuno Porcus</h4>
				<p class="Card__description">S/ 95.00</p>
			</div>
			<div class="Card">
				<img class="Card__image" src="../assets/images/promo2.png" alt="" />
				<h4 class="Card__title">Desayuno Peruano</h4>
				<p class="Card__description">S/ 193.00</p>
			</div>
		</div>
		<Footer />
	</div>
</template>

<style lang="scss">
.promo {
	position: relative;
	display: block;
	width: 100%;
	min-height: 100vh;

	&__sec{
		display: grid;
		grid-template-columns: 1fr;
		gap: 2rem;
		width: 80%;
		margin: 5rem auto;

		@media (min-width: 768px){
			width: 50%;
		}

		@media (min-width: 1024px){
			width: 80%;
			grid-template-columns: 1fr 1fr;
		}
	}
}

.Card {
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
</style>
