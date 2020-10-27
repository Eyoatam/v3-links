<template>
	<base-dialog v-if="invalidInput" title="Invalid Input" @close="closeDialog">
		<template #default>
			<p>Unfortunately, At Least One input is invalid</p>
			<p>
				Please check all inputs and make sure you enter at least a few
				characters into each input field
			</p>
		</template>
		<template #actions>
			<base-button @click="closeDialog">Ok</base-button>
		</template>
	</base-dialog>
	<base-card>
		<form>
			<div class="form-control">
				<label for="title">Title</label>
				<input id="title" name="title" type="text" ref="title" />
			</div>
			<div class="form-control">
				<label for="description">Description</label>
				<textarea
					name="description"
					id="description"
					cols="30"
					rows="3"
					ref="description"
				></textarea>
			</div>
			<div class="form-control">
				<label for="link">Link</label>
				<input id="link" name="link" type="url" ref="link" />
			</div>
			<div>
				<base-button @click.prevent="submitForm" type="submit"
					>Add Link</base-button
				>
			</div>
		</form>
	</base-card>
</template>

<script>
export default {
	inject: ['addLink'],
	data() {
		return {
			invalidInput: false,
		};
	},
	methods: {
		submitForm() {
			let enteredTitle = this.$refs.title.value;
			let enteredDescription = this.$refs.description.value;
			let enteredLink = this.$refs.link.value;
			if (
				enteredTitle.trim() === '' ||
				enteredDescription.trim() === '' ||
				enteredLink.trim === ''
			) {
				this.invalidInput = true;
				return;
			}
			this.addLink(enteredTitle, enteredDescription, enteredLink);
			this.$refs.title.value = '';
			this.$refs.description.value = '';
			this.$refs.link.value = '';
		},
		closeDialog() {
			this.invalidInput = false;
		},
	},
};
</script>

<style scoped>
label {
	font-weight: bold;
	display: block;
	margin-bottom: 0.5rem;
}

input,
textarea {
	display: block;
	width: 100%;
	font: inherit;
	padding: 0.15rem;
	border: 1px solid #ccc;
	border-radius: 7px;
	transition: 200ms ease-in-out;
}

input:focus,
textarea:focus {
	outline: none;
	box-shadow: 0 0 3pt 2pt #c1dffc;
}

.form-control {
	margin: 1rem 0;
}
</style>