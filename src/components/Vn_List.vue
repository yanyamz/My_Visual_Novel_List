<script setup>
import { ref } from '@vue/reactivity'
import VnListEntry from '@/components/Vn_List_Entry'

const visual_novels = ref([
	{
		title: 'Subarashiki Hibi ~Furenzoku Sonzai~',
		image: 'https://s2.vndb.org/cv/89/40389.jpg',
		description:
			'Subarashiki Hibi is a story told in seven chapters. The story follows a group of several Tokyo high school students mostly through July of 2012 and each chapter is told from the perspective of one of its five main characters. Because of the same timeframe coverage, certain events are overlapping from chapter to chapter but at the core of it all is a mystery revolving around the prophecy about the end of the world on July the 20th as well as the events that are following before the said date. The first part of the VN is used to make a setting for the said mysteries while the second part is about uncovering the truth behind them all.',
		rating: 86,
		tags: ['Denpa', 'Psychological', 'Mystery'],
	},
	{
		title: 'Umineko no Naku Koro ni',
		image: 'https://s2.vndb.org/cv/76/26976.jpg',
		description:
			"Umineko no Naku Koro ni takes place in the year 1986 during the time frame of October 4 and October 5 on a secluded island named Rokkenjima (六軒島). The head of a wealthy family named Kinzō Ushiromiya, who lives on and owns Rokkenjima, is near death, and eleven of his family members arrive on the island to discuss how Kinzō's assets will be divided once he is dead. Also on the island are five of Kinzō's servants, and his personal physician. After the eleven family members arrive, a typhoon traps them on the island and shortly after people start to get mysteriously murdered.",
		rating: 94,
		tags: ['Horror'],
	},
	{
		title: 'Saya no Uta',
		image: 'https://s2.vndb.org/cv/66/49766.jpg',
		description: `The story centers around Fuminori Sakisaka, a medical school student. Prior to the main storyline, he was involved in a vehicle accident that claimed the lives of both his parents and left him with critical injuries. Yet, he was rescued by experimental brain surgery that coincidentally altered his perception of the world dramatically. Everything now seems to be composed of slimy intestines and gore to him. In addition, the rest of his senses: touch, hearing, smell, and taste, are also impaired, similar to his sight, further damaging his mental health.`,
		rating: 92,
		tags: ['Horror', 'Thriller'],
	},
])
</script>

<template>
	<h1>Visual Novels</h1>
	<div class="grid">
		<VnListEntry
			v-for="visual_novel in visual_novels"
			:key="visual_novel.title"
			:visual_novel="visual_novel"
		/>
	</div>
</template>

<style lang="scss" scoped>
h1 {
	color: white;
	margin: 1rem 0;
}
.grid {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(38rem, 1fr));
	gap: 2rem;
}
</style>
