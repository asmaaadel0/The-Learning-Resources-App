<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>
<script>
export default {
  props: ["title"],
};
</script>

<style scoped>
header {
  width: 100%;
  height: 9rem;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #420084;
}

header h1 {
  color: white;
  margin: 0;
  font-family: "Times New Roman", Times, serif;
  font-size: 2000;
}
</style>