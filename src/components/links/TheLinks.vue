<template>
	<base-card>
		<base-button
			@click="toogleTabs('stored-links')"
			:mode="storedLinksButtonMode"
			>All Links</base-button
		>
		<base-button @click="toogleTabs('add-links')" :mode="addLinksButtonMode"
			>Add New Link</base-button
		>
	</base-card>
	<keep-alive>
		<component :is="selectedTab"></component>
	</keep-alive>
</template>

<script>
import StoredLinks from './StoredLinks.vue';
import AddLinks from './AddLink';
export default {
	data() {
		return {
			selectedTab: 'stored-links',
			storedLinks: [
				{
					id: 'official guide',
					title: 'Official Guide',
					description: 'The Official Vuejs documentation',
					link: 'https://vuejs.org',
				},
				{
					id: 'google',
					title: 'Google',
					description: 'This is the best place to find things',
					link: 'https://google.com',
				},
			],
		};
	},
	provide() {
		return {
			links: this.storedLinks,
			addLink: this.addLink,
			deleteLink: this.deleteLink,
		};
	},
	methods: {
		toogleTabs(tab) {
			this.selectedTab = tab;
		},
		addLink(title, description, url) {
			const newLink = {
				id: new Date().toISOString(),
				title: title,
				description: description,
				link: url,
			};
			this.storedLinks.push(newLink);
			this.selectedTab = 'stored-links';
		},
		deleteLink(id) {
			const linkIndex = this.storedLinks.findIndex((res) => res.id === id);
			this.storedLinks.splice(linkIndex, 1);
		},
	},
	computed: {
		storedLinksButtonMode() {
			return this.selectedTab === 'stored-links' ? null : 'flat';
		},
		addLinksButtonMode() {
			return this.selectedTab === 'add-links' ? null : 'flat';
		},
	},
	components: {
		AddLinks,
		StoredLinks,
	},
};
</script>