<template>
  <div class="image-card" @mouseover="mouseOver" @mouseleave="mouseLeave">
    <img :src="item.download_url" style="border-radius: 10px;" />
    <v-fade-transition>
      <div class="cover" v-show="isMouseOver">
        <div>
          <v-text-field
            solo
            v-model="title"
            class="menu"
            append-icon="mdi-chevron-down"
          ></v-text-field>
          <div class="right-btn">저장</div>
        </div>
        <div class="under-wrapper">
          <v-btn icon dark><v-icon>mdi-upload</v-icon></v-btn>
          <v-btn icon dark><v-icon>mdi-dots-horizontal</v-icon></v-btn>
        </div>
      </div>
    </v-fade-transition>
  </div>
</template>

<script>
export default {
  name: "ImageCard",
  props: ["item"],
  data() {
    return {
      isMouseOver: false,
      title: "category"
    };
  },
  methods: {
    mouseOver() {
      this.isMouseOver = true;
    },
    mouseLeave() {
      this.isMouseOver = false;
    }
  }
};
</script>

<style lang="scss" scoped>
.cover {
  position: absolute;
  top: 0;
  bottom: 7px;
  left: 0;
  right: 0;
  background-color: rgba($color: #020202, $alpha: 0.3);
  border-radius: 10px;
}
.menu {
  width: 60%;
  margin: 20px;
  border-radius: 10px 0 0 10px;
}
.right-btn {
  background-color: red;
  display: inline-block;
  width: 20%;
  height: 49px;
  position: absolute;
  right: 40px;
  top: 20px;
  color: white;
  border-radius: 0 10px 10px 0;
  line-height: 3;
  text-align: center;
}
.under-wrapper {
  position: absolute;
  bottom: 10px;
  right: 10px;
}
</style>