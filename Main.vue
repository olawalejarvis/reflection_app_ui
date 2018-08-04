<template>
  <view class="container">
    <text :style="{color: 'green', fontSize: 20}">MyVue Native App</text>
    <view :style="{borderTopWidth: 1, borderTopColor: 'gray', width: '100%'}"></view>

    <scroll-view :style="{width: '100%'}">
    <view class="border" v-for="(post, index) in posts" :key="index">
      <touchable-opacity class="flex-container" :on-press="() => handleListTap(post)">
        <image
          :style="{width: 40, height: 40, borderRadius: 25, marginRight: 8}"
          :source="{uri: post.data.thumbnail}"
        />
        <text>{{ post.data.title }}</text>
      </touchable-opacity>
    </view>
    </scroll-view>

  </view>
</template>

<script>
export default {
  props: {
    navigation: {
      type: Object
    }
  },
  mounted() {
    fetch('https://reddit.com/r/aww.json')
      .then(response => response.json())
      .then(data => {
        this.posts = data.data.children
      })
  },
  data() {
    return {
      posts: [],
    }
  },
  methods: {
    handleListTap(post) {
      this.navigation.navigate('Another', {
        imageSrc: post.data.preview.images[0].source.url
      })
    }
  }
}
</script>


<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  font-size: 20;
  color: blue;
}
.border {
  border-bottom-width: 1;
  border-color: gray;
  width: 100%;
  padding: 15;
}
.flex-container {
  flex-direction: row;
  align-items: center;
}
</style>
