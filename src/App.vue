<template>
  <div id="app" class="h-full flex">
    <sidebar v-model:active="isSidebarExpanded"/>
    <div class="flex-1">
      <navbar @expand:sidebar="isSidebarExpanded = !isSidebarExpanded"/>
      <div class="bg-fixed py-6 text-gray-800 min-h-screen router-style " v-bind="expandSidebar">
        <router-view />
      </div>
    </div>
  </div>
</template>
<script>
import navbar from './components/navbar.vue';
import sidebar from './components/sidebar.vue';

export default {
  data() {
    return {
      isSidebarExpanded: false,
    };
  },
  components: { sidebar, navbar },
  methods: {
    expandSidebar() {
      this.isSidebarHover = true;
      setTimeout(() => {
        if (this.isSidebarHover) {
          this.showSidebarText = true;
        }
      }, 100);
    },
    contractSidebar() {
      this.isSidebarHover = false;
      this.showSidebarText = false;
    },
  },
};
</script>
<style>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
