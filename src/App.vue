<template>
  <div id="testelement">

    <h1>{{ `Hello, ${name}` }}</h1>
    <p>Name: {{ name }}</p>
    <p>Age: {{ age }}</p>
    <p>Net-Worth: {{ netWorth }} $</p>


    <button @click="timeTravel(1)">Click me</button>
    <button @click="timeTravel(2)">Click me</button>
    <p> Trend: {{ trend }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Mai Bình",
      age: 20,
      netWorth: 100,
      website: "https://www.google.com",
      trend: 0,
    }
  },

  methods: {
    netWorthChange(trend) {
      if (trend < 0.75) {
        this.netWorth -= 1;
      } else {
        this.netWorth += 1;
      }
    },
    timeTravel(direction) {
      switch (direction) {
        case 1:
          this.age++;
          this.trend = Math.random();
          this.netWorthChange(this.trend);
          break;
        case 2:
          this.age--;
          this.trend = Math.random();
          this.netWorthChange(this.trend);
          break;
        default:
          break;
      }
    }
  },
}
</script>

