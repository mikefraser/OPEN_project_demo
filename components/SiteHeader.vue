<template>
	<header class="pageHeader">
		<nav>
			<app-logo/>
			<menu-toggle/>
		</nav>
	</header>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue";
import MenuToggle from "~/components/MenuToggle.vue";

export default {
  components: {
    AppLogo,
    MenuToggle
  }
};
</script>

<style lang="scss">
.pageHeader {
  margin: 1em;
}
</style>
