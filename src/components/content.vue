<template>
  <div>
    <h1>{{ title }}</h1>
    <p>input 1~100:</p>
    <input v-model="num" />
    <h1 v-bind:class="(num <= 100) & (num >= 1) ? 'green' : 'red'">
      {{ num }}
    </h1>
    <p>input a~z or A~Z:</p>
    <input v-model="str" />
    <h1 v-bind:class="test">{{ str }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    title: null
  },
  data() {
    return {
      num: null,
      str: null
    };
  },
  computed: {
    test: function() {
      if (/[A-Za-z]+/.test(this.str)) {
        return "green";
      } else return "red";
    }
  }
};
</script>

<style scoped>
.green {
  color: green;
}
.red {
  color: red;
}
</style>
