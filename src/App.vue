<template>
  <div id="app">
    <router-view/>
    <Footer/>
  </div>
</template>

<script>
import Footer from '@/components/Footer';

import '@/styles/index.scss';

export default {
  name: 'App',
  components: {
    Footer,
  },
};
</script>

<style>
#app {
  font-family: "Menlo", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-weight: 400;
  font-feature-settings: "kern", "liga";
}
.float-right {
  float: right;
}
a {
  text-decoration: none;
  background: transparent;
}
.container {
  margin: 0 auto;
  padding: 0 20px;
  max-width: 1280px!important;
}
.main, .footer {
  box-sizing: border-box;
}
.main {
  display: block;
  flex: 1;
  flex-basis: auto;
  overflow: auto;
}
::selection {
  color: #efefef;
  background: #f38030;
}
</style>
