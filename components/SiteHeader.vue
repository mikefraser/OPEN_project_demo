<template>
	<header class="pageHeader">
		<nav>
			<app-logo/>
		</nav>
	</header>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue";

export default {
  components: {
    AppLogo
  }
};
</script>

<style lang="scss">
.pageHeader {
  margin: 1em;
}
</style>
