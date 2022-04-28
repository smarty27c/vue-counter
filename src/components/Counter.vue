<template>
  <div>
    <h2>{{ counter }}</h2>
    <input name="add" v-model="counterByValue" />
    <button name="addCount" @click="updateCounterByValue">
      Increment counter By Value
    </button>
    <button name="addCount" @click="updateCounter">Increment counter</button>
  </div>
</template>


<script>
export default {
  name: "Counter",

  data() {
    return {
      counter: 0,
      counterByValue: 0,
    };
  },
  props: {
    namev: String,
  },
  methods: {
    updateCounter() {
      this.counter += 1;
    },
    updateCounterByValue() {
      this.counter = this.counter + parseInt(this.counterByValue);
    },
  },
  filters: {
    caps: function (val) {
      val = val.toString();
      return val.charAt(0).toUpperCase() + val.slice(1);
    },
  },
};
</script>