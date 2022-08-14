<template>
  <section>
    <ul>
      <li>
        <button
          class="stored-button"
          @click="setSelectedComponent('stored-goals')"
        >
          Stored Resources
        </button>
      </li>
      <li>
        <button class="add-button" @click="setSelectedComponent('add-goals')">
          Add Resources
        </button>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      inputInvalid: false,
    };
  },
  methods: {},
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
}
ul {
  background-color: rgb(255, 255, 255);
  padding: 2rem;
  padding-left: 3rem;
  margin-top: 3rem;
  text-align: center;
  width: 70%;
  border-radius: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
button {
  width: 10rem;
  height: 3rem;
}
.stored-button {
  color: aliceblue;
  border-color: rgb(74, 2, 141);
  border-radius: 0.5rem;
  background-color: rgb(74, 2, 141);
  font-size: 1rem;
  font-weight: 500;
}
.add-button {
  color: rgb(74, 2, 141);
  border-color: aliceblue;
  border-radius: 0.5rem;
  background-color: aliceblue;
  font-size: 1rem;
  font-weight: 500;
}
button:hover {
  background-color: rgba(137, 43, 226, 0.322);
  color: rgb(74, 2, 141);
  border-color: aliceblue;
}
</style>