<template>
  <div class="app-grid-fullscreen">
    <the-logo class="in-logo"></the-logo>
    <the-side-bar class="in-sidebar"></the-side-bar>
    <the-header class="in-header"></the-header>
    <!-- the router view is where all our pages are loaded -->
    <router-view class="in-main"></router-view>
    <the-footer class="in-footer"></the-footer>
  </div>
</template>

<script>
import TheLogo from "./components/ui/TheLogo.vue";
import TheSideBar from "./components/ui/TheSideBar.vue";
import TheHeader from "./components/ui/TheHeader.vue";
import TheFooter from "./components/ui/TheFooter.vue";

export default {
  components: {
    TheLogo,
    TheSideBar,
    TheHeader,
    TheFooter,
  },
  data() {
    return {
      myMsg: "hello sotiris",
    };
  },
  methods: {},
  computed: {
    token() {
      return this.$store.rootGetters.token;
    },
  },
};
</script>

<style>
html {
  font-size: 16px;
}

h1 {
  font-size: 3rem;
}
h2 {
  font-size: 2.5rem;
}
h3 {
  font-size: 2rem;
}

.app-grid-fullscreen {
  display: grid;
  grid-template-areas:
    "logo header header header header header"
    "sidebar main main main main main"
    "sidebar main main main main main"
    "sidebar main main main main main"
    "sidebar main main main main main"
    "footer footer footer footer footer footer";
  grid-gap: 1px;
}

@media only screen and (max-width: 640px) {
  .app-grid-fullscreen {
    display: grid;
    grid-template-areas:
      "logo"
      "header"
      "sidebar"
      "sidebar"
      "main"
      "main"
      "footer";
    grid-gap: 1px;
  }
}

.in-logo {
  grid-area: logo;
}
.in-header {
  grid-area: header;
}
.in-sidebar {
  grid-area: sidebar;
}
.in-main {
  grid-area: main;
}
.in-footer {
  grid-area: footer;
}
</style>
