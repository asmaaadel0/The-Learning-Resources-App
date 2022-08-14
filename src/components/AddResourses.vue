<template>
  <section>
    <form action="">
      <div>
        <label for="title">Title</label>
        <input type="text" name="title" id="title" />
      </div>
      <div>
        <label for="desc">Description</label>
        <input type="text" name="desc" id="desc" />
      </div>
      <div>
        <label for="link">Link</label>
        <input type="text" name="link" id="link" />
      </div>
      <button>Add Resourse</button>
    </form>
  </section>
</template>
<script></script>
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
  display: block;
  width: 95%;
  height: 2rem;
  border-radius: 0.5rem;
  margin-bottom: 1.5rem;
}
#desc {
  height: 4rem;
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
  background-color: rgba(137, 43, 226, 0.322);
  color: rgb(74, 2, 141);
  border-color: aliceblue;
}
</style>