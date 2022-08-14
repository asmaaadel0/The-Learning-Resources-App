<template>
  <div>
    <the-header></the-header>
    <manage-page></manage-page>
    <add-resourses></add-resourses>


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
import AddResourses from "./components/AddResourses.vue";

export default {
  components: {
    TheHeader,
    ManagePage,
    AddResourses,
  },
  data() {
    return {
      selectedComponent: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
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