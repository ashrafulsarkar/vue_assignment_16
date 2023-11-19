<script setup>
import paypal from "../assets/paypal.png";
import amazon from "../assets/amazon.png";
import github from "../assets/github.png";
import linkedin from "../assets/linkedin.png";
import reddit from "../assets/reddit.png";
import redis from "../assets/redis.png";
import microsoft from "../assets/microsoft.png";
import medium from "../assets/medium.png";

const companyLogo = [
	{
		src: github,
		alt: "github",
	},
	{
		src: microsoft,
		alt: "microsoft",
	},
	{
		src: redis,
		alt: "redis",
	},
	{
		src: amazon,
		alt: "amazon",
	},
	{
		src: paypal,
		alt: "paypal",
	},
	{
		src: linkedin,
		alt: "linkedin",
	},
	{
		src: reddit,
		alt: "reddit",
	},
	{
		src: medium,
		alt: "medium",
	},
];
</script>

<template>
	<div class="bg-secondaryBg">
		<div class="container mx-auto px-5 lg:px-0 py-16">
			<h1 data-aos="fade-up" data-aos-offset="700" data-aos-delay="200"
				class="text-2xl md:text-3xl text-heroSlate mb-7 text-center font-extrabold lg:text-4xl 2xl:text-5xl">
				Companies That Recruit Our Graduates
			</h1>
			<p data-aos="fade-up" data-aos-offset="700" data-aos-delay="400"
				class="text-base md:text-lg 2xl:text-2xl font-semibold text-center mb-14 lg:text-xl">
				Our graduates have worked in more than 400 companies around the World
			</p>
			<div class="grid items-center grid-cols-2 md:grid-cols-4 gap-14">
				<div v-for="(logo, index) in companyLogo" :key="index" data-aos-offset="700" data-aos="fade-up"
					data-aos-delay="600">
					<img :src="logo.src" :alt="logo.alt" class="mx-auto scale-75 xl:scale-90" />
				</div>
			</div>
		</div>
	</div>
</template>