<template>
  <div class="transaction">
    <div class="transaction_content max-width">
      <h2>
        —
        <img class="logo_icon" src="../static/images/logo-icon.png" />程式交易—
      </h2>
      <div class="icon1">
        <div class="icone1-1 icone1-2">
          <img src="../static/images/icon1.png" alt />
          <p>研發交易邏輯</p>
        </div>
        <div class="icone1-1 icone1-3">
          <img src="../static/images/icon2.png" alt />
          <p>回測參數調整</p>
        </div>
        <div class="icone1-1 icone1-4">
          <img src="../static/images/icon3.png" alt />
          <p>優化策略細節</p>
        </div>
        <div class="line"></div>
      </div>
      <div class="icon1_content">
        <p>
          系統程式交易，顧名思義即是將系統研發者的獨門技術指標分析見解及專業看盤觀點和風險規避準則，架構成指令群並將其寫入交易系統中，藉由程式計算出買賣點和時間。投資人依其訊號進行買進或賣出的動作，而不以自身的主觀看法進行操作。程式交易的優點在於利用電腦化的訊號，以杜絕投資人可能因為盤勢所產生的情緒化反應，進而作出不理性的交易，亦可透過一致化的交易規則，而免除追漲殺跌的操作。
        </p>
      </div>
      <h2>程式交易的優勢</h2>
      <div class="icon2">
        <a-icon
          v-for="(icon, index) in icon2s"
          :key="index"
          :src="icon.src"
          :text="icon.text"
        ></a-icon>
      </div>
      <div class="icon2_content">
        <p>
          程式交易讓您減少人為的疏失及減少花費在計算的時間，
          且相較於您靠自己人力在投資，使用程式交易讓您騰出時
          間計算分析，也能一定程度的增加投資的成果。對於沒有
          間跟精力去看盤下單的夥伴「程式交易」真的是一大福音！
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import icon2s_json from "~/assets/json/icon2.json";
import AIcon from "~/components/AIcon.vue";
export default {
  components: {
    AIcon
  },
  data: function() {
    return {
      icon2s: icon2s_json
    };
  }
};
$(window).scroll(function() {
  let scrollTop = $(this).scrollTop();
  let width = $(window).width();
  let transactionOffset = $(".transaction").offset().top;
  if (scrollTop > transactionOffset - 300) {
    $(".icone1-2").addClass("animation");
    $(".icone1-4").addClass("animation");
    $(".icon1 .line").addClass("animation");
  }
  if (scrollTop > transactionOffset + 100) {
    $(".icon2-1").addClass("animation");
  }
});
</script>

<style>
.transaction {
  background: #baddf9;
  height: 1100px;
}

.transaction_content h2 {
  text-align: center;
  width: 100%;
  padding: 50px 0px 30px 0px;
  font-size: 30px;
  letter-spacing: 3px;
}

.logo_icon {
  margin: 6px 6px -3px;
}

.icon1 .icone1-1 {
  width: 180px;
  height: 180px;
  border: 8px solid #002f6c;
  border-radius: 50%;
  background: #edffff;
  position: relative;
  z-index: 1;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 80px;
}

.icone1-2 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.icone1-4 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@keyframes icon4 {
  0% {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  100% {
    position: absolute;
    top: 10%;
    left: 80%;
    transform: translate(-50%, -50%);
  }
}

.icon1 .icone1-1 p {
  position: absolute;
  bottom: -70px;
  left: calc(50% - 108px / 2);
  font-size: 18px;
  font-weight: bold;
  letter-spacing: 1px;
}

.icon1 {
  display: flex;
  justify-content: space-around;
  position: relative;
}

.icon1 img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.icon1 .line {
  width: 0px;
  height: 8px;
  background: #002f6c;
  position: absolute;
  top: 50%;
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

@keyframes line {
  0% {
    width: 0;
  }
  100% {
    width: 900px;
  }
}

.icon1_content {
  margin: 100px auto 30px auto;
  width: 70vw;
  font-weight: 300;
}

.icon1_content p {
  line-height: 30px;
  font-size: 18px;
  margin-top: 300px;
  letter-spacing: 1px;
}

.company h2.animation {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}
.company_text.animation {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.2s;
  animation-fill-mode: forwards;
}
.icone1-2.animation {
  animation-name: icon2;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}
.icone1-4.animation {
  animation-name: icon4;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}
.icon1 .line.animation {
  animation-name: line;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
  margin-top: 80px;
}

.icon1 .line.animation {
  animation-name: line;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
  margin-top: 80px;
}

.icon2 > div {
  width: 120px;
}

.icon2 {
  display: flex;
  justify-content: space-evenly;
}

.icon2 > div > p {
  text-align: center;
  font-size: 18px;
  font-weight: bold;
}

.icon2_content {
  margin: 30px auto;
  width: 70vw;
  line-height: 30px;
  font-weight: 300;
  font-size: 18px;
  letter-spacing: 1px;
}
</style>
