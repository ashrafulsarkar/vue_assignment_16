<script setup>
import { ref, onMounted, onUnmounted } from "vue";

import burgerMenu from "../assets/navbar.svg";
import closeMenu from "../assets/close.svg";
import logo from "../assets/logo.svg";

const burger = ref(null);
const showMenu = ref(false);
const toggleNav = () => {
	showMenu.value = !showMenu.value;
	burger.value.src = showMenu.value ? closeMenu : burgerMenu;
};

const isScrolled = ref(false);
const handleScroll = () => {
	isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
	window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
	window.removeEventListener("scroll", handleScroll);
});

const links = [
	{ label: "Home", href: "#" },
	{ label: "Features", href: "#features" },
	{ label: "About Us", href: "#about" },
	{ label: "Testimonial", href: "#testimonial" },
	{ label: "Call to Action", href: "#calltoaction" },
];
</script>

<template>
	<header id="manuSection" class="pb-32" data-aos="fade-right">
		<nav :class="{ 'bg-[#f7f7ff]/50 backdrop-blur-md': isScrolled,
			'bg-transparent': !isScrolled, }" class="p-5 xl:px-7 w-full fixed z-50" style="transition: background-color 0.3s ease-in-out">
			<div class="flex container justify-between mx-auto items-center gap-14">
				<div class="logo">
					<img :src="logo" alt="suxz" class="lg:scale-110" />
				</div>
				<div class="menu">
					<ul class="hidden lg:flex gap-12 lg:mt-[2px]">
						<li v-for="(link, index) in links" :key="index">
							<a :href="link.href" class="text-colorNav font-bold hover:text-secondaryPurple duration-300 ease-in-out">{{ link.label }}</a>
						</li>
					</ul>
				</div>
				<div class="relative z-50">
					<ul class="lg:flex hidden mt-[2px] items-center gap-9">
						<li>
							<a href="#" class="font-semibold text-secondaryPurple">Log in</a>
						</li>
						<button type="button"
							class="px-7 py-[0.63rem] rounded-lg font-semibold text-white bg-secondaryPurple duration-200 ease-in-out hover:bg-[#F7F7FD] hover:text-slate-400">
							Sign up
						</button>
					</ul>
					<button @click="toggleNav" class="block lg:hidden focus:outline-none">
						<img :src="burgerMenu" alt="burger" ref="burger" />
					</button>
				</div>

				<!-- mobile nav -->
				<ul :class="showMenu ? 'left-0 grid' : 'left-[-100%] grid'"
					class="pt-5 mobile-menu h-screen w-[100%] md:w-1/2 fixed duration-500 lg:hidden ease-in-out content-start space-y-8 md:space-y-5 top-0 left-0 pl-[1.19rem] xs:pl-6 bg-white md:pl-12">
					<li v-for="(link, index) in links" :key="index">
						<a :href="link.href" class="text-colorNav font-semibold md:text-lg">{{ link.label }}</a>
					</li>
					<li>
						<a href="#" class="font-semibold block text-secondaryPurple">Log in</a>
					</li>
					<li>
						<a href="#" class="text-white bg-secondaryPurple rounded-lg md:py-3 px-7 md:px-20 xs:px-12 py-2 font-semibold">Sign up</a>
					</li>
				</ul>
			</div>
		</nav>
	</header>
</template>
<style scoped>
#manuSection {
    z-index: 9;
    position: relative;
}
</style>