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
  margin: 1rem;

  nav {
    position: relative;
    height: 48px;

    &:before {
      content: "";
      display: block;
      position: absolute;
      height: 1px;
      left: 0;
      right: 0;
      top: 23.5px;
      background: $highlight_lite;
      margin: 10px;
    }

    .logo,
    button {
      position: absolute;
    }
    .logo {
      width: 200px;
      height: 48px;
      padding: 8px;
      top: 4.5px;
      left: 0;
    }
    button {
      right: 0;
      top: 0.24px;
    }
  }
}
</style>
