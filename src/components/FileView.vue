<template>
  <div class="file">
    <img :src="require(`../assets/icons/${fileType}_icon.png`)" alt="">
    <div class="name">{{name}}</div>
  </div>
</template>

<script>
export default {
  name: 'FileView',
  props: {
    name: String,
    type: String
  },
  computed: {
    fileType() {
      switch(this.type) {
        case 'application/octet-stream':
          return 'browserslistrc';
        case 'application/javascript':
          return 'js';
        case 'application/json':
          return 'json';
        case 'image/jpeg':
          return 'jpg';
        case 'image/png':
          return 'png';
        case 'image/svg':
          return 'svg';
        default: 
          return 'txt';
      }
    }
  }

}
</script>

<style scoped lang="scss">
.file {
  width: 90px;
  padding: .3rem;
  margin: 7px;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: green;
  background-color: rgba(233, 241, 247, .3);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 5px;
  cursor: pointer;
  transition: all .3s;
}
.file:hover {
  background-color: white;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.36);
}
.name {
  word-break: break-all;
  text-align: center;
}

</style>
