<script setup>
import bootcampAvatar from "../assets/bootcamp.jpg";
import superstarAvatar from "../assets/superstar.jpg";
import starterAvatar from "../assets/starter.jpg";
import premiumAvatar from "../assets/premium.jpg";

const featureSectionData = [
	{
		src: starterAvatar,
		alt: "starter avatar",
		title: "Starter",
		description: "Free class access for that start learning code and design",
	},
	{
		src: premiumAvatar,
		alt: "premium avatar",
		title: "Premium",
		description: "Advanced material from the Starter & learn to build projects",
	},
	{
		src: superstarAvatar,
		alt: "superstar avatar",
		title: "Superstar",
		description: "Materials for experts who have completed the premium package",
	},
	{
		src: bootcampAvatar,
		alt: "bootcamp avatar",
		title: "Bootcamp",
		description:
			"Informatics science training program with the latest material",
	},
];

const FeatureSection = [
	{
		src: featureSectionData[0].src,
		alt: featureSectionData[0].alt,
		title: featureSectionData[0].title,
		description: featureSectionData[0].description,
		aosDelay: 400,
	},
	{
		src: featureSectionData[1].src,
		alt: featureSectionData[1].alt,
		title: featureSectionData[1].title,
		description: featureSectionData[1].description,
		aosDelay: 800,
	},
	{
		src: featureSectionData[2].src,
		alt: featureSectionData[2].alt,
		title: featureSectionData[2].title,
		description: featureSectionData[2].description,
		aosDelay: 1200,
	},
	{
		src: featureSectionData[3].src,
		alt: featureSectionData[3].alt,
		title: featureSectionData[3].title,
		description: featureSectionData[3].description,
		aosDelay: 1600,
	},
];
</script>

<template>
	<div id="features" class="bg-secondaryBg pb-12 lg:-mt-4 xl:-mt-10">
		<div class="container mx-auto px-5 xs:px-3 md:px-6 lg:px-9 xl:px-14 py-10">
			<div class="mb-16">
				<h5 data-aos="fade-right" data-aos-delay="200" data-aos-offset="400"
					class="uppercase text-sm mb-2 tracking-widest font-bold 2xl:text-xl md:text-base lg:text-lg text-secondaryPurple">
					FEATURES
				</h5>
				<h2 data-aos="fade-right" data-aos-delay="600" data-aos-offset="400"
					class="text-2xl md:text-3xl md:max-w-sm lg:max-w-lg md:leading-10 lg:leading-[2.8rem] lg:text-4xl 2xl:text-5xl 2xl:max-w-2xl 2xl:leading-[4rem] mb-6 text-heroSlate font-extrabold">
					Online Learning Platform International Curriculum
				</h2>
				<p data-aos="fade-right" data-aos-delay="800" data-aos-offset="400"
					class="text-heroSlate md:text-lg lg:text-xl 2xl:text-2xl 2xl:max-w-lg 2xl:leading-10 max-w-sm md:leading-relaxed text-base font-semibold">
					Study and understand the material class is more relaxed without time limit.
				</p>
			</div>
			<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 items-center">
				<!-- cards -->
				<div v-for="(page, index) in FeatureSection" :key="index" data-aos="zoom-in" :data-aos-delay="page.aosDelay"
					data-aos-offset="450">
					<div class="group">
						<div :class="{ 'p-[1.6rem]': index === 0, }" class="bg-white group-hover:bg-secondaryPurple duration-300 ease-in-out shadow-sm rounded-lg p-6 py-8">
							<img :src="page.src" :alt="page.alt" class="scale-110 mb-8 rounded-md" />
							<h3 class="text-heroSlate group-hover:text-white duration-300 ease-in-out font-extrabold text-2xl mb-4">
								{{ page.title }}
							</h3>
							<p class="text-base group-hover:text-white duration-300 ease-in-out md:text-lg text-heroSlate mb-9">
								{{ page.description }}
							</p>
							<a href="#" class="w-full block text-center rounded-lg tracking-wide py-2 text-white bg-cardsTeal font-semibold">See Class</a>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>