<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/fire.png" />
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home'
}
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  margin: 0 auto;
  width: 200px;
  height: 200px;
}
.home::before {
  content: url("~@/assets/fire-yellow.png");
  position: absolute;
  left: calc(50% - 5px);
  top: calc(50% - 5px);
  transform: translate(-50%, -50%);
  clip: rect(0, 200px, 0, 0);
  animation: noise 2s infinite linear alternate-reverse;
}
.home::after {
  content: url("~@/assets/fire-red.png");
  position: absolute;
  left: calc(50% + 5px);
  top: calc(50% + 5px);
  transform: translate(-50%, -50%);
  clip: rect(0, 200px, 0, 0);
  animation: noise-other 3s infinite linear alternate-reverse;
}
@keyframes noise {
  @for $i from 1 through 50 {
    #{$i*2%} {
      clip: rect(random(200) + px, 300px, random(200) + px, 0);
    }
  }
}
@keyframes noise-other {
  @for $i from 1 through 100 {
    #{$i*1%} {
      clip: rect(random(200) + px, 300px, random(200) + px, 0);
    }
  }
}
</style>
