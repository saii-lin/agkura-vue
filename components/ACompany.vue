<template>
  <div :class="['company', animated ? 'animation' : '']">
    <div class="company_text max-width">
      <div class="company_text-box">
        <h2>
          —
          <img class="logo_icon" src="/images/logo-icon.png" alt />公司團隊—
        </h2>
        <p>
          來自世界各地的金融優秀人才，擁有技術精湛的專業分析能力
          ，以及優化客戶服務的堅持，共同學習，相互協作。我們在各
          地均設有服務據點，提供完整的技術服務，若您對AGKURA有
          任何需求與問題，隨時可諮詢我們的服務人員，取得專業建議。
        </p>
      </div>
    </div>
    <div class="company_pic company_pic1 pc"></div>
    <div class="company_pic company_pic2 pc"></div>
    <div class="company_text max-width">
      <div class="company_text-box">
        <h2>
          —
          <img class="logo_icon" src="/images/logo-icon.png" alt />公司願景—
        </h2>
        <p class="company_text1">
          在金融投資產業深耕，整合過往的投資操作實務經驗，
          以現今的軟體技術為服務核心，幫助客戶於自動化、智能化的金融投資中取得優
          勢，並於互動之中強化客戶投資理念，提昇客戶交易勝率，達成雙贏共利的目標。
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    animated: {
      type: Boolean
    }
  }
};
</script>

<style>
.max-width {
  max-width: 1280px;
  margin: 0 auto;
}
.company {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(2, 1fr);
  background: #baddf9;
  /* height: 100vh; */
  overflow: hidden;
}

.company_pic1 {
  background: url(/images/about1.jpeg);
  transform: translatex(-300px);
  filter: opacity(0);
}

@keyframes company_pic1 {
  0% {
    filter: opacity(0);
    transform: translatex(-300px);
  }
  100% {
    filter: opacity(1);
    transform: translatex(0px);
  }
}

.company_pic2 {
  background: url(/images/about2.jpeg);
  transform: translatex(300px);
  filter: opacity(0);
}

@keyframes company_pic2 {
  0% {
    filter: opacity(0);
    transform: translatex(300px);
  }
  100% {
    filter: opacity(1);
    transform: translatex(0px);
  }
}

.company_pic {
  width: 100%;
  height: 100%;
  background-size: cover;
}

.ph1 {
  display: none;
}

.ph2 {
  display: none;
}

.company h2 {
  text-align: center;
  filter: opacity(0);
  letter-spacing: 3px;
}

.company_text {
  width: 50vw;
  position: relative;
  filter: opacity(0);
  display: grid;
  justify-items: center;
  align-items: center;
}

.company_text p {
  line-height: 30px;
  font-weight: 300;
  font-size: 18px;
  letter-spacing: 1px;
}

.company_text-box {
  width: 50%;
  margin: 20px 0px;
}

.animation .company_pic1 {
  animation-name: company_pic1;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}
.animation .company_pic2 {
  animation-name: company_pic2;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}
.company.animation h2 {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}
.animation .company_text {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.2s;
  animation-fill-mode: forwards;
}
</style>
