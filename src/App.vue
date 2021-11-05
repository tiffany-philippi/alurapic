<template>
  <div class="body">
    <h1 class="title text-center">{{ title }}</h1>
    <ul class="photos-list">
      <li v-for="photo of photos" class="item-list">
        <app-card-panel :title="photo.titulo">
          <img :src="photo.url" :alt="photo.titulo" class="photo" />
        </app-card-panel>
      </li>
    </ul>
  </div>
</template>

<script>
import Panel from './components/shared/panel/Panel.vue';
export default {
  components: {
    'app-card-panel': Panel
  },
  data() {
    return {
      title: "Alurapic",
      photos: []
    };
  },
  created() {
    this.$http
      .get("http://localhost:3000/v1/fotos")
      .then(res => res.json())
      .then(
        photos => (this.photos = photos),
        err => console.log(err)
      );
  }
};
</script>

<style lang="scss">
.body {
  font-family: Helvetica, sans-serif;
  width: 96%;
  margin: 0 auto;

  .photos-list {
    display: flex;
    list-style: none;
    flex-wrap: wrap;
    .item-list {
      margin: 0 10px 40px;
    }
  }
}
.text-center {
  text-align: center;
}
</style>
