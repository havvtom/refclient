<template>
	<div class="flex bg-gray-500">
		<div class="w-1/3 text-center">
			{{ referral.email }}
		</div>
		<div class="w-1/3 text-center">
			{{ dateCreated }}
		</div>
		<div class="w-1/3 text-center">
			<div class="flex justify-center">
				<p>{{ referral.completed }}</p>
				<p v-if="!referral.completed" class="text-blue-500 ml-3">
					<a href="">link</a>
				</p>
			</div>
		</div>
	</div>
</template>

<script type="text/javascript">
	import moment from 'moment'
	export default{
		props:{
			referral: {
				required: true,
				type: Object
			}
		},
		computed: {
			dateCreated () {
				return moment(this.referral.created_at).fromNow()
			}
		}
	}
</script>