<template>
	<footer class="Footer">
		<div class="Footer__container">
			<div class="Footer__block">
				<h6 class="Footer__subtitle">Atendemos todos los dias</h6>
				<p class="Footer__info">
					Martes y Miércoles (Salón): 8:30 am - 4:00 pm <br />
					Martes y Miércoles (Rappi / Recojo en tienda): 4:30 pm - 8:30 pm
					<br />
					Jueves, Viernes y Sábado: 8:30 am - 11:00 pm <br />
					Domingo: 8:30 am - 04:00 pm
				</p>
			</div>
			<div class="Footer__block">
				<h6 class="Footer__subtitle">Dirección</h6>
				<p class="Footer__info">Cl. Cmdt. Juan G Moore 176, Miraflores</p>
			</div>
			<div class="Footer__block">
				<h6 class="Footer__subtitle">Teléfono</h6>
				<p class="Footer__info">
					946 207 656 <br />
					(01) 301 4726
				</p>
			</div>
			<div class="Footer__block">
				<h6 class="Footer__subtitle">Siguenos en</h6>
				<div class="Footer__links">
					<a class="Footer__link" href="">
						<img
							class="Footer__ico"
							src="../assets/icons/facebook.svg"
							alt=""
						/>
					</a>
					<a class="Footer__link" href="">
						<img
							class="Footer__ico"
							src="../assets/icons/instagram.svg"
							alt=""
						/>
					</a>
				</div>
			</div>
		</div>
	</footer>
</template>

<style lang="scss">
.Footer {
	padding: 6rem 0;
	background: #000;
	font-size: 3rem;

	@media (min-width: 1024px) {
		padding: 8rem 0;
	}

	&__container {
		display: grid;
		grid-template-columns: 1fr;
		gap: 4rem;
		width: 80%;
		margin: 0 auto;

			@media (min-width: 1024px) {
				grid-template-columns: 1fr 1fr;
				gap: 3rem;
			}
	}

	&__block {
	}

	&__subtitle {
		margin-bottom: 1rem;
		color: #cca86a;
		font-size: 1.4rem;
		font-weight: 500;
		font-family: "Oswald";
		letter-spacing: 1px;
	}

	&__info {
		color: #fff;
		font-weight: 600;
		letter-spacing: 1px;
    line-height: 2;
	}

	&__links {
		display: flex;
		align-items: center;
		gap: 1rem;
    margin-top: 2rem;
	}

	&__link {
		display: block;
	}

	&__ico {
		display: block;
		width: 1.2rem;
		height: auto;
	}
}
</style>
