<template>
	<div>
		<div class="flex">
			<div class="text-center text-lg text-gray-700 w-1/3">
				Email
			</div>
			<div class="text-center text-lg text-gray-700 w-1/3">
				Date Created
			</div>
			<div class="text-center text-lg text-gray-700 w-1/3">
				Completed
			</div>
		</div>
		<Referral v-for="referral in referrals" :key="referral.id" :referral="referral"/>
	</div>
</template>

<script type="text/javascript">
	export default {
		data () {
			return {
				referrals: []
			}
		},
		async asyncData({ app, params }) {
	      let referrals = await app.$axios.get(`referrals`)

	      return {
	      	referrals: referrals.data.data
	      }
	    }
	}
</script>