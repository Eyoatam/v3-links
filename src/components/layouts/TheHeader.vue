<template>
	<header>
		<h1>{{ title }}</h1>
	</header>
</template>

<script>
export default {
	props: ['title'],
};
</script>

<style scoped>
header {
	background: #eee;
	box-shadow: 0px 10px 5px 0 rgba(0, 0, 0, 0.08);
	padding: 1rem;
	margin-bottom: 3rem;
	text-align: center;
}
</style>