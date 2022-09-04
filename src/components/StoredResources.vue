<template>
  <section>
    <h2>{{ title }}</h2>
    <p>{{ description }}</p>
    <a :href="link">View Resource</a>
    <button @click="$emit('delete', id)">Delete</button>
  </section>
</template>

<script>
export default {
  emits: ["choosenButton", "delete"],
  props: {
    id: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
  },
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
section {
  padding: 0;
  margin: 0 auto 0 auto;
  background-color: rgb(255, 255, 255);
  padding: 2.9rem;
  padding-top: 1rem;
  margin-top: 3rem;
  width: 70%;
  border-radius: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
h2 {
  font-size: 140%;
  font-weight: 700;
  display: inline;
}
p {
  font-size: 130%;
  font-weight: 500;
}
a {
  color: rgb(255, 119, 0);
  text-decoration: none;
  font-size: 110%;
  font-weight: 500;
}
a:hover{
  color: rgb(251, 154, 43);
}
button {
  color: rgb(74, 2, 141);
  border-color: aliceblue;
  border-radius: 0.5rem;
  background-color: aliceblue;
  font-size: 110%;
  font-weight: 500;
  left: 20rem;
  /* margin-left: 55rem; */
  width: 10rem;
  height: 3.3rem;
  display: inline;
  float: right;
}
button:hover {
  background-color: rgba(137, 43, 226, 0.322);
  color: rgb(74, 2, 141);
  border-color: aliceblue;
}
@media (max-width: 450px) {
  a {
    display: block;
  }
  section {
    height: 11rem;
    text-align: center;
  }
  button {
    margin-top: 1rem;
    float: none;
  }
}
</style>