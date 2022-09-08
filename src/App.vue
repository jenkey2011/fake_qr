<template>
    <div>
      <PersonInfo v-show="!showFakePass" @myClick="onClick"></PersonInfo>
      <fake v-show="showFakePass" @clickToReturn="back" :personalInfo="personalInfo"/>
    </div>
</template>

<script>
import PersonInfo from './components/PersonInfo.vue'
import fake from './components/fake.vue'

export default {
  components: { fake, PersonInfo },
  data() {
    return {
      showFakePass: true,
      personalInfo: {
        name: "明蕊",
        stdId: 2020111690,
        dep: "电子工程学院",
        inOut: "允许出校",
        // img: require("@/img/default.jpg"),
        img: require("@/img/mr.png"),
      },
    };
  },
  mounted() {
    document.body.addEventListener("touchstart", () => {});
  },
  methods: {
    onClick(pi) {
      this.personalInfo = pi;
      this.showFakePass = true;
    },
    back() {
      this.showFakePass = false;
    },
  },
};
</script>

<style>

</style>
