<template>
	<div>
		{{ project }}
	</div>
</template>

<script type="text/javascript">
	export default {
		async asyncData({ app, params }) {
			let response = await app.$axios.$get(`/projects/${params.id}`)

			return {
				project: response.data
			}
		}
	}
</script>