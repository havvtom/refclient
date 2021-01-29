<template>
	<div class="ml-5 bg-gray-100 mt-10">
		<h2 class="text-xl text-gray-700">
			{{ project.title }}
		</h2>
		<p>
			{{ project.description }}
		</p>
	</div>
</template>

<script type="text/javascript">
	export default {
		props: {
			project: {
				required: true,
				type: Object
			}
		}
	}
</script>