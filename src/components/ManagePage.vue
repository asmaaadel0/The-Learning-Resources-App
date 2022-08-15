<template>
  <section>
    <ul>
      <li>
        <button
          :class="firstButton ? 'select-button' : 'not-select-button'"
          class="stored-button"
          @click="setSelectedComponent('stored-goals')"
        >
          Stored Resources
        </button>
      </li>
      <li>
        <button
          :class="secondButton ? 'select-button' : 'not-select-button'"
          @click="setSelectedComponent('add-goals')"
        >
          Add Resources
        </button>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  emits: ["choosenButton"],
  props: {},
  data() {
    return {
      firstButton: true,
      secondButton: false,
    };
  },
  methods: {
    setSelectedComponent(buttonClicked) {
      this.$emit("choosenButton", buttonClicked);
      if (buttonClicked === "stored-goals") {
        this.firstButton = true;
        this.secondButton = false;
      } else {
        this.firstButton = false;
        this.secondButton = true;
      }
    },
  },
};
</script>
<style scoped>
ul {
  list-style: none;
  display: flex;
  padding: 0;
  gap: 1rem;
  margin: 0 auto 0 auto;
  display: grid;
  grid-template-columns: 0.1fr 0.1fr;
  background-color: rgb(255, 255, 255);
  padding: 2.9rem;
  padding-left: 3rem;
  margin-top: 3rem;
  text-align: center;
  width: 70%;
  border-radius: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
button {
  width: 10rem;
  height: 3.3rem;
}
.select-button {
  color: aliceblue;
  border-color: rgb(74, 2, 141);
  border-radius: 0.5rem;
  background-color: rgb(74, 2, 141);
  font-size: 110%;
  font-weight: 500;
}
.not-select-button {
  color: rgb(74, 2, 141);
  border-color: aliceblue;
  border-radius: 0.5rem;
  background-color: aliceblue;
  font-size: 110%;
  font-weight: 500;
}
button:hover {
  color: aliceblue;
  border-color: rgb(74, 2, 141);
  background-color: rgb(74, 2, 141);
  /* background-color: rgba(137, 43, 226, 0.322);
  color: rgb(74, 2, 141);
  border-color: aliceblue; */
}
@media (max-width: 450px) {
  li {
    margin-left: 3.5rem;
  }
  ul {
    grid-template-columns: 0;
  }
}
@media (max-width: 300px) {
  li {
    margin-left: 1rem;
  }
  ul {
    grid-template-columns: 0;
  }
}
</style>