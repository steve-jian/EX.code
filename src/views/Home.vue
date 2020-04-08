<template>
  <div>
    <h1>{{ getMessage() }}</h1>
    <h2>{{ message }}</h2>
    <button @click="asyncMessage">Click me</button>
    <button @click="local">Show location</button>
    <h2>
      {{ location }}
    </h2>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      message: "",
      location: "",
    };
  },
  methods: {
    getMessage() {
      return "Hi I am a sync message";
    },
    asyncMessage() {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve("I am an async message");
        }, 1000);
      }).then((res) => {
        this.message = res;
      });
    },
    local() {
      let api =
        "https://api.mapbox.com/geocoding/v5/mapbox.places/yunlin.json?access_token=pk.eyJ1Ijoic3RldmUxOTk5IiwiYSI6ImNrOHAxMGFyNzFiaG4zbGwzNjM5dzVmM3UifQ.Y1r0Pt22JU9aMno4_mcSAA";
      return this.axios.get(api).then((res) => {
        let place = res.data.features[0].place_name;
        let coordinate = `${res.data.features[0].center[1]}, ${res.data.features[0].center[0]}`;
        this.location = `${place} at ${coordinate}`;
      });
    },
  },
};
</script>
