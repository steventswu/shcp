<template>
  <section class="container">
    <video class="vid" autoplay loop muted>
      <source src="~/assets/video/2016SHCP_showreel.mp4" type="video/mp4">
    </video>
  </section>
</template>

<script>
export default {
  head() {
    return {
      title: 'Stay High Crew Production',
      meta: [
        { name: 'keywords', content: 'stayhighcrew proudction, stayhighcrew, phate, mj116'},
        { hid: 'description', name: 'description', content: 'Stayhighcew Production Home page'},
      ]
    }
  }
}
</script>

<style scoped>
.container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}
.vid {
  min-height: 100%;
  min-width: auto;
}
</style>
