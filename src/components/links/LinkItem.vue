<template>
	<li>
		<base-card>
			<header>
				<h3>{{ title }}</h3>
				<base-button mode="warning" @click="deleteLink(id)">Delete</base-button>
			</header>
			<p>{{ description }}</p>
			<nav>
				<a :href="link" target="_blank">Open Url</a>
			</nav>
		</base-card>
	</li>
</template>

<script>
export default {
	props: ['id', 'title', 'description', 'link'],
	inject: ['deleteLink'],
};
</script>

<style scoped>
li {
	margin: auto;
	max-width: 40rem;
}

header {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

h3 {
	font-size: 1.25rem;
	margin: 0.5rem 0;
}

p {
	margin: 0.5rem 0;
}

a {
	text-decoration: none;
	color: #068fff;
	transition: 100ms ease-in-out;
}

a:hover,
a:active {
	color: #068fff9d;
}
</style>