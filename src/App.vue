<template>
  <div>
    <the-header></the-header>
    <manage-page @choosenButton="choosenButtonFunction"></manage-page>
    <keep-alive>
      <stored-resources
        v-show="firstButton"
        v-for="resource in resources"
        :key="resource.id"
        :id="resource.id"
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
      ></stored-resources>
    </keep-alive>
    <add-resourses
      v-if="secondButton"
      @add-resource="AddResource"
    ></add-resourses>

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
      resources: [
        {
          title: "Official Guide",
          description: "The official Vue.js documentation",
          link: "http://google.com",
        },
      ],
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
    AddResource(title, description, link) {
      const newResurce = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link,
      };
      this.resources.push(newResurce);
      this.firstButton = true;
      this.secondButton = false;
    },
    deleteResource(resourceId) {
      this.resources = this.resources.filter(
        (resource) => resource.id !== resourceId
      );
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