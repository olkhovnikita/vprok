<template>
  <div class="wrap">
    <Header />
    <Advantages />
    <div class="process">
      <Process />
    </div>
    <ToBuys />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Advantages from "./components/Advantages.vue";
import Process from "./components/Process.vue";
import ToBuys from "./components/ToBuys.vue";
import Footer from "./components/Footer.vue";
export default {
  name: "App",
  components: {
    Header,
    Advantages,
    Process,
    ToBuys,
    Footer,
  },
  data() {
    return {
      slideId: 1,
    };
  },
};
</script>

<style scoped>
.wrap {
  max-width: 1920px;
  margin: 0 auto;
  position: relative;
}

</style>
