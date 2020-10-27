<template>
	<the-header title="Useful Links"></the-header>
	<the-links></the-links>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheLinks from './components/links/TheLinks.vue';
export default {
	components: {
		TheHeader,
		TheLinks,
	},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;700&display=swap');

* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

html {
	font-family: 'Nunito', sans-serif;
}

body {
	margin: 0;
	background: #eee;
}
</style>