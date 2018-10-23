<template>
  <div>
    <site-header/>
    <nuxt/>
  </div>
</template>

<script>
import SiteHeader from "~/components/SiteHeader.vue";

export default {
  components: {
    SiteHeader
  }
};
</script>

<style lang="scss">
*,
*:before,
*:after {
  box-sizing: border-box;
}

html {
  background-color: $bkground_col;
  margin: 0;
  min-height: 100vh;
}

body {
  min-height: 100vh;
}
</style>

