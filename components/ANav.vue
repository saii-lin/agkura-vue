<template>
  <nav>
    <img class="logo" src="/images/logo.png" alt v-scroll-to="'header'" />
    <ul>
      <li class="language">
        <a href="/cn/index.html">简体中文</a>/
        <a href="/zh/index.html">繁體中文</a>
      </li>
      <li id="index" v-scroll-to="'header'">首頁</li>
      <li id="transaction" v-scroll-to="{ el: '.transaction', offset: -50 }">
        程式交易
      </li>
      <li id="about" v-scroll-to="{ el: '.about', offset: -50 }">
        為何選擇AGKURA
      </li>
      <li id="address" v-scroll-to="{ el: '.email', offset: -50 }">連絡我們</li>
    </ul>
  </nav>
</template>

<script>
export default {};
</script>

<style>
nav {
  background: #baddf9;
  position: fixed;
  width: 100%;
  z-index: 10;
  box-shadow: 10px 0 10px #424746;
  top: 0px;
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
