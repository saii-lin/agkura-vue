<template>
  <div>
    <div class="icon2-1"><img :src="src" alt /></div>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String
    },
    text: {
      type: String
    }
  }
};
</script>

<style scoped>
.icon2-1 p {
  text-align: center;
}

.icon2-1 {
  background: #edffff;
  width: 100px;
  height: 100px;
  position: relative;
  border: 8px solid #002f6c;
  border-radius: 50%;
  filter: opacity(0);
}

@keyframes icon2 {
  0% {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  100% {
    position: absolute;
    top: 10%;
    left: 20%;
    transform: translate(-50%, -50%);
  }
}

@keyframes icon2-1 {
  0% {
    filter: opacity(0);
    transform: translatey(10px);
  }
  100% {
    filter: opacity(1);
    transform: translatey(0px);
  }
}

.icon2-1 img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.icon2-1 p {
  position: absolute;
  bottom: -60px;
  left: calc(50% - 91px / 2);
  font-size: 14px;
}
.icon2-1.animation {
  animation-name: icon2-1;
  animation-duration: 0.8s;
  animation-fill-mode: forwards;
}
</style>
