<template>
  <div>
    <a-nav></a-nav>
    <a-header></a-header>
    <a-transaction> </a-transaction>
  </div>
</template>

<script>
import ANav from "~/components/ANav.vue";
import AHeader from "~/components/AHeader.vue";
import ATransaction from "~/components/ATransaction.vue";

export default {
  components: {
    ANav,
    AHeader,
    ATransaction
  }
};
</script>

<style>
body {
  font-family: "Noto Sans SC", "Noto Sans TC", sans-serif;
  background: #baddf9;
}
</style>
<style scoped></style>
