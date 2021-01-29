<template>
	<div class="flex justify-center">
		<div class="mt-10 w-2/3">
			<form>
				<div class="mb-6">
					<label class="block mb-2 uppercase font-bold text-xs text-gray-700"
						for="name" 
					>
						Title
					</label>

					<input 
						class="border border-blue-400 rounded-lg p-2 w-full" 
						type="text"
						v-model="form.title" 
						id="name"
						required
					>
				</div>
				<div class="mb-6">
					<label class="block mb-2 uppercase font-bold text-xs text-gray-700"
						for="name" 
					>
						Description
					</label>
					<div class="border border-blue-400 rounded-lg py-4 px-8">
						<textarea
				            class="w-full outline-none"
				            v-model="form.description"
				            placeholder="What's up doc"
				            autofocus
				        >                        
				        </textarea>
					</div>
				</div>
				<div class="flex">
					<button
					class="bg-blue-600 hover:bg-blue-400 uppercase text-xs text-white py-2 px-6 mr-6 rounded-full"
					@click.prevent="submit"
					>
						Create Project
					</button>
					<button
					class="bg-blue-600 hover:bg-blue-400 uppercase text-xs text-white py-2 px-6 rounded-full"
					@click.prevent="submit"
					>
						Cancel
					</button>
				</div>
			</form>
		</div>
	</div>
</template>

<script type="text/javascript">
	export default {
		data () {
			return {
				form: {
					title: '',
					description: ''
				}
			}
		},
		methods: {
			submit () {
				this.$axios.$post(`projects`, this.form)
			}
		}
	}
</script>