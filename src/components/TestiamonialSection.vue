<script setup>
import jason from "../assets/jason.png";
import jean from "../assets/jean.png";
import cassandra from "../assets/cassandra.png";
import peter from "../assets/peter.png";

const testimoni = [
	{
		src: jason,
		alt: "jason",
		name: "Jason Todd",
		job: "Enterpreneur",
		text: `"The mentor is cool, how to convey each material is also detailed and easy to understand.."`,
	},
	{
		src: cassandra,
		alt: "cassandra",
		name: "Cassandra K",
		job: "Web Designer",
		text: `"The mentor is cool, how to convey each material is also detailed and easy to understand.."`,
	},
	{
		src: peter,
		alt: "peter",
		name: "Peter Parker",
		job: "PHP Enthusiast",
		text: `"The mentor is cool, how to convey each material is also detailed and easy to understand.."`,
	},
	{
		src: jean,
		alt: "jean",
		name: "Jean Gray",
		job: "Designer",
		text: `"The mentor is cool, how to convey each material is also detailed and easy to understand.."`,
	},
];

const testimonies = [
	{
		src: testimoni[0].src,
		alt: testimoni[0].alt,
		name: testimoni[0].name,
		job: testimoni[0].job,
		text: testimoni[0].text,
		aosDelay: 400,
	},
	{
		src: testimoni[1].src,
		alt: testimoni[1].alt,
		name: testimoni[1].name,
		job: testimoni[1].job,
		text: testimoni[1].text,
		aosDelay: 800,
	},
	{
		src: testimoni[2].src,
		alt: testimoni[2].alt,
		name: testimoni[2].name,
		job: testimoni[2].job,
		text: testimoni[2].text,
		aosDelay: 1200,
	},
	{
		src: testimoni[3].src,
		alt: testimoni[3].alt,
		name: testimoni[3].name,
		job: testimoni[3].job,
		text: testimoni[3].text,
		aosDelay: 1600,
	},
];
</script>

<template>
	<div id="testimonial" class="container mx-auto py-16 px-5 xl:px-10">
		<div class="text-center mb-20">
			<h5 data-aos="fade-up" data-aos-offset="770" data-aos-delay="200"
				class="uppercase text-sm mb-2 tracking-widest font-bold 2xl:text-xl md:text-base lg:text-lg text-secondaryPurple">
				TESTIMONIAL
			</h5>
			<h2 data-aos="fade-up" data-aos-offset="770" data-aos-delay="400"
				class="text-2xl md:text-3xl lg:text-4xl 2xl:text-5xl mb-6 text-heroSlate font-extrabold">
				OUR ALUMNI SAY
			</h2>
			<p data-aos="fade-up" data-aos-offset="770" data-aos-delay="600"
				class="text-heroSlate md:text-lg lg:text-xl 2xl:text-2xl text-base font-semibold mb-9">
				These are the words of people who have taken our class
			</p>
		</div>
		<div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 xl:gap-12 gap-20 items-center">
			<div v-for="(testimony, index) in testimonies" :key="index" data-aos="zoom-in"
				:data-aos-delay="testimony.aosDelay" data-aos-offset="770"
				class="border relative py-12 px-8 border-secondaryPurple rounded-lg">
				<img :src="testimony.src" :alt="testimony.alt" class="absolute -top-10 left-0 right-0 mx-auto" />
				<div class="pt-8">
					<h1 class="text-2xl text-heroSlate text-center mb-2 font-extrabold">
						{{ testimony.name }}
					</h1>
					<h3 class="text-slate-400 text-base lg:text-lg text-center font-semibold mb-8">
						{{ testimony.job }}
					</h3>
					<p class="text-base text-center lg:text-lg leading-relaxed text-heroSlate font-semibold">
						{{ testimony.text }}
					</p>
				</div>
			</div>
		</div>
	</div>
</template>