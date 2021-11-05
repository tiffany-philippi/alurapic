<template>
  <div class="panel text-center">
    <h2 class="photo-title">{{ title }}</h2>
    <slot class="content-panel"></slot>
  </div>
</template>

<script>
export default {
  props: ['title'],
};
</script>

<style lang="scss">
.panel {
  display: flex;
  flex-direction: column;
  border: 1px solid #d4ddeb;
  margin: 5px;
  box-shadow: 5px 5px 10px grey;
  width: 200px;
  height: auto;
  vertical-align: top;
  .photo-title {
    background-color: #fdf054;
    margin: 0;
    text-transform: uppercase;
    padding: 10px;
  }
}
</style>
