<template>
  <section>
    <form action="" @submit.prevent="submitData">
      <div>
        <label for="title">Title</label>
        <input type="text" name="title" id="title" v-model="title" />
      </div>
      <div>
        <label for="desc">Description</label>
        <textarea
          type="text"
          name="desc"
          id="desc"
          v-model="description"
          rows="6"
        />
      </div>
      <div>
        <label for="link">Link</label>
        <input type="url" name="link" id="link" v-model="link" />
      </div>
      <button>Add Resourse</button>
    </form>
    <teleport to="body">
      <error-alert v-if="inputInvalid">
        <div id="invalid">
          <header>
            <h2>Invalid Input</h2>
          </header>
          <p>Unfortunately, at least one input valye is invalid.</p>
          <p>
            please check all inputs and make sure you enter at least a few
            characters into each input field.
          </p>
          <button @click="confirmError">okay</button>
        </div>
      </error-alert>
    </teleport>
  </section>
</template>
<script>
import ErrorAlert from "./ErrorAlert.vue";
export default {
  components: {
    ErrorAlert,
  },
  emits: ["add-resouce"],
  data() {
    return {
      title: "",
      description: "",
      link: "",
      inputInvalid: false,
    };
  },
  methods: {
    submitData() {
      if (
        this.title.trim() === "" ||
        this.description.trim() === "" ||
        this.link.trim() === ""
      ) {
        this.inputInvalid = true;
        return;
      }
      this.$emit("add-resource", this.title, this.description, this.link);
    },
    confirmError() {
      this.inputInvalid = false;
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
  margin-top: 3rem;
  width: 70%;
  border-radius: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}
label {
  display: block;
  font-weight: 600;
  font-size: 130%;
}
input {
  height: 2rem;
}
input,
textarea {
  display: block;
  width: 95%;
  border-radius: 0.5rem;
  margin-bottom: 1.5rem;
}
button {
  width: 10rem;
  height: 3.3rem;
  color: aliceblue;
  border-color: rgb(74, 2, 141);
  border-radius: 0.5rem;
  background-color: rgb(74, 2, 141);
  font-size: 110%;
  font-weight: 500;
}
button:hover {
  background-color: rgb(88, 2, 169);
  /* color: rgb(74, 2, 141); */
  border-color: aliceblue;
}
input:focus,
textarea:focus {
  background-color: rgb(219, 190, 253);
  color: rgb(32, 5, 63);
  border-color: rgb(32, 5, 63);
}
#invalid button {
  float: right;
  margin: 1rem;
}
#invalid p {
  padding: 1rem;
}
#invalid header {
  color: white;
  width: 100%;
  padding: 1rem;
  height: 3rem;
  display: flex;
  /* justify-content: center; */
  /* align-items: right; */
  background-color: rgb(74, 2, 141);
}
#invalid h2 {
  margin: 0.8rem;
}
@media (max-width: 450px) {
  #invalid header {
    height: 5rem;
  }
}
</style>