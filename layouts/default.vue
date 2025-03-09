<template>
  <div>
    <div class="page">
      <div class="page">
        <nuxt />
      </div>
      <div class="footerFifi">Philip Gazagnes - 06.73.51.74.46</div>
    </div>
  </div>
</template>

<script>
export default {};
</script>
<style>
body {
  background-color: var(--primaryColor);
}
.page {
  color: white;
  font-family: 'Open Sans', sans-serif;
  /* background: rgba(255, 255, 255, 0.1);
  width: 1300px;
  margin: 50px auto;
  padding: 30px; */
}
.anim {
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 0;
}
.page {
  position: relative;
  z-index: 1;
}
.footerFifi {
  text-align: center;
  padding: 0 0 150px 0;
}
</style>
