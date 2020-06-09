<template>
  <div class="about">
    <div class="about_content max-width">
      <h2>—為何選擇AGKURA—</h2>
      <div class="about_text">
        <p>
          AGKURA擁有多年金融交易系統研發經驗，提供交易軟體產品客製化與專業交易程式編寫服務，
          服務對象遍佈亞洲與太平洋地區。
        </p>
        <p>從單一交易邏輯程式編碼到整體自動化交易解決方案，多方位為投資人和機構投資者提供服務。</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
$(window).scroll(function() {
  let scrollTop = $(this).scrollTop();
  let width = $(window).width();
  let aboutOffset = $(".about").offset().top;
  if (scrollTop > aboutOffset - 400) {
    $(".about h2").addClass("animation");
    $(".about_text").addClass("animation");
  }
});
</script>

<style>
.max-width {
  max-width: 1280px;
  margin: 0 auto;
}
.about {
  background: url(../static/images/about3.jpg) no-repeat;
  background-size: cover;
  height: 100vh;
}

.about h2 {
  margin: 0;
  padding-top: 180px;
  color: #fff;
  filter: opacity(0);
  letter-spacing: 3px;
}

.about_text {
  width: 500px;
  filter: opacity(0);
  margin-left: 10px;
}

.about_text p {
  color: #fff;
  line-height: 30px;
  font-weight: 300;
  letter-spacing: 1px;
  font-size: 18px;
}
.about_text.animation {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-delay: 0.3s;
  animation-fill-mode: forwards;
}
.about h2.animation {
  animation-name: headerTitle;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
}
</style>