<template>
  <div class="loader-container" v-if="loading">
    <div class="loaders">
      <div class="ball-clip-rotate">
        <div clas="ball"></div>
      </div>
    </div>
  </div>
</template>

<script>
import "loaders.css"

export default {
  computed: {
    loading() {
      return this.$store.state.loading.isLoading;
    }
  }
};
</script>

<style lang="scss" scoped>
$theme-color:#25b290;
.loader-container {
  position: fixed;
  top: 0;
  z-index: 999;
  width: 100%;
  height: 100vh;
  background-color: #eee;
  opacity: 0.7;
}

.ball-clip-rotate > div {
  border: 2px solid $theme-color;
  /* background-color: orange !important; */
  border-bottom-color: transparent !important;
}

.ball-clip-rotate {
  position: absolute;
  top: 50%;
  color: red;
  transform: translate(-50%, -50%);
  left: 50%;
}
</style>