<template>
  <div>
    <the-header></the-header>
    <manage-page @choosenButton="choosenButtonFunction"></manage-page>
    <stored-resources v-if="firstButton"></stored-resources>
    <add-resourses v-if="secondButton"></add-resourses>

    <!-- <active-goals v-if="selectedComponent=== 'active-goals'"></active-goals>
    <manage-goals v-if="selectedComponent=== 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
import ManagePage from "./components/ManagePage.vue";
import StoredResources from "./components/StoredResources.vue";
import AddResourses from "./components/AddResourses.vue";

export default {
  components: {
    TheHeader,
    ManagePage,
    AddResourses,
    StoredResources,
  },
  data() {
    return {
      firstButton: true,
      secondButton: false,
    };
  },
  methods: {
    choosenButtonFunction(buttonClicked) {
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

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>