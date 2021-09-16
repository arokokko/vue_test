<template>
  <div class="folder">
    <img :src="require(`@/assets/icons/open_folder_icon.png`)" alt="">
    <div class="name">{{name}}</div>
  </div>
  
  <div class="subfolder">
    <template v-for="folder in folders" :key="folder.name">
      <FolderView :name="folder.name" :folders="folder.folders" :files="folder.files" />
    </template>
  </div>
  
  <div class="files">
    <template v-for="file in files" :key="file.name">
      <FileView :name="file.name" :type="file.type"/>
    </template>
  </div>
    
</template>

<script>
import FileView from "./FileView";
export default {
  name: 'FolderView',
  components: {FileView},
  props: {
    name: String,
    folders:Array,
    files:Array
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.folder {
  width: 90px;
  padding: .2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: orangered;
  background-color: rgba(233, 241, 247, .5);
  border-radius: 5px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .26);
  transition: all .3s;
  cursor: pointer;
  grid-column-start: 1;
  grid-column-end: 3;
}
.folder:hover {
  background-color: white;
  box-shadow: 0 2px 12px rgba(0, 0, 0, .36);
}
.subfolder {
  display: grid;
  grid-template-columns: repeat(2, 50px) 1fr;
  gap: .5rem;
  grid-column-start: 2;
  grid-column-end: 4;
}
.files {
  display: flex;
  flex-wrap: wrap;
  grid-column-start: 2;
  grid-column-end: 4;
}

@media (max-width: 576px) {
  .subfolder {
    grid-template-columns: 25px 25px 1fr;
  }
}

</style>
