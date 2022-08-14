<template>
    <h2>Manage Goals</h2>
    <input type="text" name="" id="" ref="goal" />
    <button @click="setGoal">Set Goals</button>
    <teleport to="body">
      <error-alert v-if="inputInvalid">
        <h2>input is invalid</h2>
        <p>please input valid value</p>
        <button @click="confirmError">okay</button>
      </error-alert>
    </teleport>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";
export default {
  
  components: {
    ErrorAlert,
  },
  data() {
    return {
      inputInvalid: false,
    };
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      if (enteredValue === "") {
        this.inputInvalid = true;
      }
    },
    confirmError() {
      this.inputInvalid = false;
    },
  },
};
</script>