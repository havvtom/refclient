<template>
	<div>
		<div class="flex justify-between items-center px-3 pt-6">
	        <h1 class="text-gray-700 text-sm font-normal capitalize">
		        <nuxt-link :to="{ name: 'index' }">My Projects </nuxt-link> / {{ project.title }}
		    </h1>
	        <button
	          class="bg-blue-400 hover:bg-blue-400 uppercase text-xs text-white py-2 px-6 mr-6 rounded-full"
	        >
	            Create Project
	        </button>
      	</div>
	      <div>
	      		<div class="md:flex mt-10">
	      			<div class="md:w-3/4 pl-3 md:mr-3 mr-0">
	      				<div class="mb-8">
		      				<h2 class="text-gray-700 text-lg font-normal">Tasks</h2>
		      				<!-- Tasks -->
		      				<div class="bg-white mt-3 md:mt-0 rounded py-3 px-3">
		      					Lorem Ipsum
		      				</div>
	      				</div>
	      				<div class="mb-8">
		      				<h2 class="text-gray-700 text-lg font-normal mb-3">General Notes</h2>
		      				<!-- general notes -->
		      				<div class="border border-blue-400 rounded-lg py-4 px-8">
								<textarea
						            class="w-full outline-none"
						            placeholder="What's up doc"
						            autofocus
						        >                        
						        </textarea>
							</div>
	      				</div>
	      			</div>
	      			<div :to="{ name: 'projects-id', params: { id: project.id } }" class="bg-white mt-10 md:mt-0 rounded shadow  py-3 h-48 md:w-1/4 px-3">
						<h2 class="font-normal p-3 border-l-4 border-blue-400 capitalize text-xl text-gray-900 py-4">
							{{ project.title }}
						</h2>
						<p class="text-gray-500 p-3">
							{{ project.description }}
						</p>
					</div>
	      		</div>
	      </div>
	</div>
</template>

<script type="text/javascript">
	export default {
		data () {
			return {
				project: {}
			}
		},
		async asyncData({ app, params }) {
			let response = await app.$axios.$get(`/projects/${params.id}`)

			return {
				project: response.data
			}
		}
	}
</script>