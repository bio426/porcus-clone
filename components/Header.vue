<template>
	<header class="Header" :class="{ 'Header--hide': shouldHide }">
		<div class="Header__container">
			<img class="Header__logo" src="../assets/images/logo-small.png" alt="" />
			<nav class="Header__links">
				<NuxtLink class="Header__link" to="/">Inicio</NuxtLink>
				<NuxtLink class="Header__link" to="/menu">Carta</NuxtLink>
				<NuxtLink class="Header__link" to="/promotions">Promociones</NuxtLink>
			</nav>
			<button class="Header__button" @click="showDropdown = !showDropdown">
				<img class="Header__ico" src="../assets/icons/menu.svg" alt="" />
			</button>
		</div>
		<transition name="dropdown">
			<div class="Header__dropdown" v-if="showDropdown">
				<nav>
					<NuxtLink class="Header__dlink" to="/">Inicio</NuxtLink>
					<NuxtLink class="Header__dlink" to="/menu">Carta</NuxtLink>
					<NuxtLink class="Header__dlink" to="/promotions"
						>Promociones</NuxtLink
					>
				</nav>
			</div>
		</transition>
	</header>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue"

let shouldHide = ref(false)
let isLarge = ref(false)

function handleScroll(e: Event) {
	if (isLarge.value && window.scrollY < 180) {
		shouldHide.value = true
	} else {
		shouldHide.value = false
	}
}
onMounted(() => window.addEventListener("scroll", handleScroll))
onBeforeUnmount(() => window.removeEventListener("scroll", handleScroll))
let largeMq: MediaQueryList
let showDropdown = ref(false)
onMounted(() => {
	largeMq = window.matchMedia("(min-width: 1024px)")
	if (largeMq.matches) isLarge.value = true
	largeMq.addEventListener("change", (ev) => {
		if (ev.matches) {
			showDropdown.value = false
			isLarge.value = true
			shouldHide.value = true
		} else {
			isLarge.value = false
			shouldHide.value = false
		}
	})
	shouldHide.value = isLarge.value
})
</script>

<style lang="scss">
.Header {
	position: relative;
	width: 100%;
	background: #fff;
	transition: all 1s ease;
	opacity: 1;
	z-index: 10;

	@media (min-width: 1024px) {
		position: fixed;
		top: 0;

		&--hide{
			top: -5rem;
			opacity: 0;
		}
	}

	&__container {
		display: flex;
		justify-content: space-between;
		width: 80%;
		margin: 0 auto;
	}

	&__logo {
		width: 4rem;
		height: auto;
	}

	&__links {
		display: none;
		align-items: center;
		gap: 2rem;

		@media (min-width: 1024px) {
			display: flex;
		}
	}

	&__link {
		display: block;
		color: rgba($color: #000000, $alpha: 60%);
		font-weight: 600;
		font-family: "Oswald";
		text-decoration: none;
		letter-spacing: 2px;
		transition: all 0.5s ease;

		&:hover {
			opacity: 70%;
		}
	}

	&__button {
		display: block;
		background: none;
		border: none;
		outline: none;

		@media (min-width: 1024px) {
			display: none;
		}
	}

	&__dropdown {
		position: absolute;
		top: 100%;
		left: 50%;
		transform: translateX(-50%);
		width: 80%;
		padding: 1rem;
		background: #fff;
		border-top: 2px solid #cca86a;
		opacity: 1;

		@media (min-width: 768px) {
			padding: 3rem;
		}
	}

	&__dlink {
		display: block;
		color: #666666;
		font-family: "Oswald";
		text-decoration: none;

		&:not(:last-child) {
			margin-bottom: 1rem;
		}
	}

	&__ico {
		display: block;
		width: 1.5rem;
	}

	.router-link-active {
		color: #cca86a;
	}
}

.dropdown-enter-active,
.dropdown-leave-active {
	transition: all 0.5s ease;
}

.dropdown-enter-from,
.dropdown-leave-to {
	// top: -10rem;
	opacity: 0;
}
</style>
