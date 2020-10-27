<template>
	<ul>
		<link-item
			v-for="res in links"
			:key="res.id"
			:id="res.id"
			:title="res.title"
			:description="res.description"
			:link="res.link"
		></link-item>
	</ul>
</template>

<script>
import LinkItem from './LinkItem.vue';
export default {
	inject: ['links'],
	components: {
		LinkItem,
	},
};
</script>

<style scoped>
ul {
	list-style: none;
	margin: 0 auto;
	padding: 0;
	max-width: 40rem;
}
</style>