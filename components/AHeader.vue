<template>
  <header>
    <div class="mask"></div>
    <div class="hreder_content">
      <div class="blue">
        <div class="hreder_text">
          <h2>將投資「自動化處理」</h2>
          <div class="hreder_text_p">
            <p>
              在金融市場賺錢是很多投資者都嚮往的事,
              但這種專業能力並不可一蹴而成的。
              加上大部份投資人都缺乏研究和看盤買賣的時間，
              所以近年越來越流行的程式交易, 或許就是您等待已久的夢幻工具。
            </p>
            <div
              class="understanding"
              v-scroll-to="{ el: '.transaction', offset: -50 }"
            >
              馬上了解→
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style>
header {
  background: url(/images/back1-1280x852.jpg) no-repeat;
  background-size: cover;
  height: 100vh;
  position: relative;
}

header .mask {
  position: absolute;
  width: 100%;
  height: 100%;
  background: black;
  opacity: 0.2;
  z-index: 0;
}

header .hreder_content {
  position: absolute;
  z-index: 1;
  width: 100%;
}

header h2 {
  font-size: 30px;
  letter-spacing: 3px;
}

.blue {
  height: 100vh;
  width: 0;
  background: #002f6c;
  opacity: 80%;
  animation-name: blueAnim;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
  display: grid;
  justify-content: center;
  align-content: center;
}

@keyframes blueAnim {
  from {
    width: 0;
    filter: opacity(0);
  }
  to {
    width: 50vw;
    filter: opacity(1);
  }
}
.hreder_text h2 {
  color: #fff;
  filter: opacity(0);
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}

.hreder_text p {
  width: 345px;
  font-size: 18px;
  line-height: 30px;
  color: #fff;
  font-weight: lighter;
  filter: opacity(0);
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.6s;
  animation-fill-mode: forwards;
  letter-spacing: 1px;
}

@keyframes headerTitle {
  0% {
    filter: opacity(0);
    transform: translateY(20px);
  }
  100% {
    filter: opacity(1);
    transform: translatey(0px);
  }
}

.understanding {
  width: 84px;
  float: right;
  background: #baddf9;
  padding: 10px;
  border-radius: 5px;
  font-weight: bold;
  color: #002f6c;
  transition: 0.5s;
  cursor: pointer;
  filter: opacity(0);
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.7s;
  animation-fill-mode: forwards;
}

.understanding:hover {
  color: #fff;
  background: rgb(125, 0, 129);
}
</style>
