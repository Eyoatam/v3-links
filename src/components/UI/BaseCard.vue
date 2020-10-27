<template>
	<div>
		<slot></slot>
	</div>
</template>

<style scoped>
div {
	border-radius: 12px;
	box-shadow: -8px -8px 8px 0 rgba(255, 255, 255, 1),
		8px 8px 8px 0 rgba(0, 0, 0, 0.05);
	padding: 1rem;
	margin: 2rem auto;
	max-width: 40rem;
}
</style>