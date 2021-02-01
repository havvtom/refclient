<template>
	<div class="md:w-1/3 px-3 py-6">
		<div class="bg-white h-48 rounded shadow py-3">
		<nuxt-link :to="{ name: 'projects-id', params: { id: project.id } }" class=" mt-10">
			<h2 class="font-normal p-3 border-l-4 border-blue-400 capitalize text-xl text-gray-900 py-4">
				{{ project.title }}
			</h2>
			<p class="text-gray-500 p-3">
				{{ project.description }}
			</p>
		</nuxt-link>
		</div>
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