<template>
  <div class="fullpage_img">
    <div class="container">
    <video autoplay muted loop id="trailer">
      <source src="./../assets/trailer.mp4" type="video/mp4">
    </video>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FullSizeContent',
  props: {
    playVideo: Boolean
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@media only screen and (max-width: 1000px) {
  .fullpage_img {
    width: 1000px !important;
    margin-left: 50%;
    transform: translateX(-50%);
  }
}
.fullpage_img {
  width: 100%;
  display: flex;
  position: relative;
  max-height: 100vh;
  overflow: hidden;
  -webkit-box-shadow: 0px 9px 15px 4px rgb(0 0 0); 
  box-shadow: 0px 9px 15px 4px rgb(0 0 0)
}

.fullpage_img .container {
  display: flex;
  align-items: flex-end;
  width: 100%;
}

#trailer {
  width: inherit;
  z-index: -1;
}
</style>
