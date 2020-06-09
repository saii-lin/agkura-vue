<template>
  <div>
    <a-nav></a-nav>
    <div class="body" @scroll="onScroll">
      <a-header></a-header>
      <a-transaction
        ref="transaction"
        :animated-top="transactionAnimatedTop"
        :animated-bottom="transactionAnimatedBottom"
      ></a-transaction>
      <a-about ref="about" :animated="aboutAnimated"></a-about>
      <a-company ref="company" :animated="companyAnimated"></a-company>
      <a-email></a-email>
      <a-footer></a-footer>
    </div>
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
  },
  data: () => ({
    transactionAnimatedTop: false,
    transactionAnimatedBottom: false,
    aboutAnimated: false,
    companyAnimated: false
  }),
  mounted() {
    console.log(this.$refs);
  },
  methods: {
    onScroll(e) {
      console.log(e.target.scrollTop);
      const scrollTop = e.target.scrollTop;
      const transactionOffsetTop = this.$refs.transaction.$el.offsetTop;
      const aboutOffsetTop = this.$refs.about.$el.offsetTop;
      const companyOffsetTop = this.$refs.company.$el.offsetTop;
      if (
        !this.transactionAnimatedTop &&
        scrollTop > transactionOffsetTop - 250
      ) {
        this.transactionAnimatedTop = true;
      } else if (
        !this.transactionAnimatedBottom &&
        scrollTop > transactionOffsetTop + 100
      ) {
        this.transactionAnimatedBottom = true;
      } else if (!this.aboutAnimated && scrollTop > aboutOffsetTop - 350) {
        this.aboutAnimated = true;
      } else if (!this.companyAnimated && scrollTop > companyOffsetTop - 250) {
        this.companyAnimated = true;
      }
    }
  }
};
</script>

<style>
body {
  font-family: "Noto Sans SC", "Noto Sans TC", sans-serif;
  background: #baddf9;
}
</style>
<style scoped>
.body {
  margin-top: 58px;
  max-height: calc(100vh - 58px);
  overflow: auto;
}
</style>
