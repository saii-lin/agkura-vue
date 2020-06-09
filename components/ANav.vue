<template>
  <nav>
    <img class="logo" src="../static/images/logo.png" alt />
    <ul>
      <li class="language">
        <a href="/cn/index.html">简体中文</a>/
        <a href="/zh/index.html">繁體中文</a>
      </li>
      <li id="index">首頁</li>
      <li id="transaction">程式交易</li>
      <li id="about">為何選擇AGKURA</li>
      <li id="address">連絡我們</li>
    </ul>
    <div class="hbg">
      <div class="hbg_line top"></div>
      <div class="hbg_line on"></div>
      <div class="hbg_line bottom"></div>
    </div>
  </nav>
</template>

<script>
export default {};
$(".hbg").click(function() {
  hbg();
});
$("#index").click(function() {
  $("html,body").animate({ scrollTop: $("header").offset().top }, 666);
  hbg();
});
$("#transaction").click(function() {
  $("html,body").animate(
    { scrollTop: $(".transaction").offset().top - 50 },
    666
  );
  hbg();
});
$("#about").click(function() {
  $("html,body").animate({ scrollTop: $(".about").offset().top }, 666);
  hbg();
});
$("#address").click(function() {
  $("html,body").animate({ scrollTop: $(".email").offset().top - 50 }, 666);
  hbg();
});
$(".logo").click(function() {
  $("html,body").animate({ scrollTop: $("header").offset().top - 50 }, 666);
  hbg();
});
$(".understanding").click(function() {
  $("html,body").animate(
    { scrollTop: $(".transaction").offset().top - 50 },
    666
  );
});
function hbg() {
  $(".hbg").toggleClass("active");
  $(".top").toggleClass("active");
  $(".bottom").toggleClass("active");
  $(".on").toggleClass("active");
  $("nav ul").toggleClass("active");
}
</script>

<style>
nav {
  background: #baddf9;
  position: fixed;
  width: 100%;
  z-index: 10;
  box-shadow: 10px 0 10px #424746;
}

nav .logo {
  width: 150px;
  margin: 10px;
  position: absolute;
  cursor: pointer;
}

nav ul {
  list-style: none;
  display: flex;
  justify-content: flex-end;
  margin: 0;
}

nav li {
  padding: 10px;
  margin: 10px;
  color: #424746;
  font-weight: bold;
  cursor: pointer;
  transition: 0.5s;
}

nav li:hover {
  color: #ffffff;
  background: #002f6c;
  border-radius: 5px 5px 5px 5px;
}

.language a {
  text-decoration: none;
  color: #002f6c;
  transition: 0.5s;
}

.language a:hover {
  color: #fff;
}

.language:hover {
  background: transparent;
}

.hbg {
  display: none;
}
</style>
