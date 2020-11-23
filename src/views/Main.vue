<template>
  <div class="main-view">
    <div
      v-masonry
      transition-duration="0"
      item-selector=".item"
      column-width="100"
      gutter="10"
      fit-width="true"
      class="masonry-container"
    >
      <image-card
        v-masonry-tile
        class="item"
        v-for="(item, index) in images"
        :key="index"
        :item="item"
      >
      </image-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "Main",
  components: { ImageCard: () => import("@/components/main/ImageCard.vue") },
  data() {
    return {
      images: []
    };
  },
  beforeMount() {
    this.requestImageList();
  },
  methods: {
    requestImageList() {
      this.$http.get("https://picsum.photos/v2/list").then(res => {
        console.log(res.data);
        let parsedImage = res.data.map(el => {
          let tmpArr = el.download_url.split("/");
          let deleted = tmpArr.splice(-2, 2);
          console.log(deleted);
          tmpArr.push(
            `300/${Math.floor((deleted[1] / deleted[0]) * 300)}.webp`
          );
          el.download_url = tmpArr.join("/");
          return el;
        });
        this.images = parsedImage;
        console.log(this.images);
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.main-view {
  padding: 20px;
}
.masonry-container {
  margin: 0 auto;
}
.item {
  margin-bottom: 10px;
}
</style>