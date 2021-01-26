<template>
	<div>
		tiripo palocal host yamdara
	</div>
</template>

<script type="text/javascript">
	export default {
		created () {
			this.$cookies.set('referral', this.$route.query.referral, {
		    path: '/',
		    maxAge: 60 * 60 * 24 * 365
		  })
		}
	}
</script>