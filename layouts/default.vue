<template>
  <div>
    <site-header/>
    <section class="container"> 
      <nuxt/>
    </section>
    <site-footer/>
  </div>
</template>

<script>
import SiteHeader from "~/components/SiteHeader.vue";
import SiteFooter from "~/components/SiteFooter.vue";

export default {
  components: {
    SiteHeader,
    SiteFooter
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
.container {
  min-height: 80vh;
}
</style>

