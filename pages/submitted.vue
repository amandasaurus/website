<template>
	
	<nuxt-content :document="submittedPage" class="homepage"></nuxt-content>

</template>

<script>
export default {
	name: "submitted",
	head() {
		return {
			title: "Eintrag eingereicht",
			meta: [
				{
					hid: "robots",
					name: "robots",
					content: "noindex"
				}
			]
		}
	},
	async asyncData({ $content }) {
		const submittedPage = await $content("submitted").fetch();
		return { submittedPage }
	}
}
</script>

<style scoped>
.nuxt-content {
	padding: 20px;
	max-width: 750px;
	text-align: center;
	position: initial;
	font-size: 20px;
}

.nuxt-content >>> p {
	line-height: 1.4em;
	margin: 30px 0;
	text-align: center;
}

.nuxt-content >>> h2 {
	margin-top: 50px;
}

.nuxt-content >>> a[href="/"] {
	border: 0;
	text-decoration: none;
	color: white;
	background-color: var(--color-dark);
	box-shadow: 0 3px 6px var(--color-box-shadow);
	cursor: pointer;
	font-size: 16px;
	display: inline-flex;
	align-items: center;
	font-weight: 600;
	padding: 8px 10px;
	border-radius: 4px;
	outline: 0;
	transition: 0.12s ease background-color;
	font-family: 'Poppins', sans-serif;
}

.nuxt-content >>> a[href="/"]:hover, .nuxt-content >>> a[href="/"]:focus {
	background-color: var(--color-dark-accent);
}

.nuxt-content >>> a[href="/"]:active {
	background-color: var(--color-dark-active);
}
</style>