<template>
  <TheHeader></TheHeader>
  <div class="wrapper">
    <FolderView name="$" :folders="folders" :files="files" />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import FolderView from './components/FolderView.vue';
import data from './data/list';

export default {
  name: 'App',
  components: {
    FolderView,
    TheHeader
  },
  data: () => data
}
</script>

<style >
body {
  position: relative;
  margin: 0;
  background-color: rgb(233, 241, 247);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.wrapper {
  display: grid;
  grid-template-columns: repeat(2, 50px) 1fr;
  gap: .3rem;
  max-width: 60%;
  margin: 0 auto;
  padding: 2rem;
  font-size: .8rem;
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .26);
}
img {
  width: 3rem;
  height: 3rem;
}

@media (max-width: 992px) {
  .wrapper {
    max-width: 100%;
  }
}

@media (max-width: 576px) {
  .wrapper {
    grid-template-columns: repeat(2, 25px) 1fr;
    font-size: 1rem;
    padding: 1rem .2rem;
  }
}

</style>
