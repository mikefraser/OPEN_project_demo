<template>
	<header class="projHead">
		<div class="projHead_mask">
			<img class="projHead_imgMain" src="~/assets/img/fasque/headerPic.jpg"/>
		</div>
		<div class="projHead_text">
			<h1>Fasque</h1>
			<h4>Architecture | Landscape</h4>
		</div>
	</header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.projHead {
  //   background-color: lightcoral;

  height: 60vh;
  position: relative;
  //   transform: translate3d(0, 0, 0);
  //   overflow: hidden;
  display: flex;
  justify-content: center;

  &_mask {
    position: fixed;
    z-index: -1;
  }
  &_imgMain {
    display: block;
    width: 100%;
    height: 60vh;
    top: 0;
    object-fit: cover;
    z-index: -1;
  }
  &_text {
    position: absolute;
    width: 100%;
    bottom: 0;
    padding: 5vw;
    color: $bkground_col;

    h1,
    h4 {
      color: inherit;
      text-shadow: 4px 4px 16px rgba(0, 0, 0, 0.8);
      max-width: 30em;
      margin: 2rem 0 1rem;
    }
  }
}
</style>
