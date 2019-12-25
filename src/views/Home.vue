<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <br />
    <Content title="v-model & v-bind" />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Footer from "@/components/theFooter.vue";
import Content from "@/components/content.vue";

export default {
  name: "home",
  components: {
    Content,
    Footer
  }
};
</script>
