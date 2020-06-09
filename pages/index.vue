<template>
  <div>
    <a-nav></a-nav>
    <a-header></a-header>
    <a-transaction></a-transaction>
    <a-about></a-about>
    <a-company></a-company>
    <a-email></a-email>
    <a-footer></a-footer>
  </div>
</template>

<script>
import ANav from "~/components/ANav.vue";
import AHeader from "~/components/AHeader.vue";
import ATransaction from "~/components/ATransaction.vue";
import AAbout from "~/components/AAbout.vue";
import ACompany from "~/components/ACompany.vue";
import AEmail from "~/components/AEmail.vue";
import AFooter from "~/components/AFooter.vue";

export default {
  components: {
    ANav,
    AHeader,
    ATransaction,
    AAbout,
    ACompany,
    AEmail,
    AFooter
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
