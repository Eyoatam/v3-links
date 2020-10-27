<template>
	<button :class="mode">
		<slot></slot>
	</button>
</template>

<script>
export default {
	props: ['mode'],
};
</script>

<style scoped>
button {
	font-weight: bold;
	font-family: 'Nunito', sans-serif;
	font-size: 1em;
	border: none;
	outline: none;
	background: #008afc;
	cursor: pointer;
	color: #fff;
	padding: 0.6rem;
	border-radius: 5px;
	transition: 200ms ease-in-out;
}

button:hover {
	background: #006fca;
}

.flat {
	background: transparent;
	color: #234866;
}

.flat:hover {
	background-color: #c1dffc;
}

.flat:active {
	background: #008afc;
	color: #fff;
}

.warning {
	background: #e70045;
}

.warning:hover {
	background: #9b002f;
}
</style>