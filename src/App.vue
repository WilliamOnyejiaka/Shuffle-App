<template>
  <router-view></router-view>
  <!-- <Footer/> -->
</template>

<script>
import ShuffleView from "./views/ShuffleView.vue";
import Footer from "./components/Footer.vue";

export default {
  components:{
    ShuffleView,
    Footer
  }
}
</script>