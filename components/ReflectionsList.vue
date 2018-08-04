<template>
  <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent :on-press="() => onPressNav()">
          <nb-icon :name="'menu'" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Daily Reflections</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>

    <!-- Contents Here -->
    <nb-content>
      <nb-card v-for="i in 5" :key="i">
        <nb-card-item header bordered>
          <nb-text>12 July, 2018 Reflection</nb-text>
        </nb-card-item>
        <nb-card-item bordered>
          <nb-body>
            <nb-text>
              NativeBase is a free and open source framework that enable developers to build high-quality mobile apps using React Native iOS and Android apps with a fusion of ES6.
            </nb-text>
          </nb-body>            
        </nb-card-item>
        <nb-card-item footer bordered>
          <touchable-opacity :on-press="() => onPressRead()"> 
            <nb-text> Read </nb-text>
          </touchable-opacity>
        </nb-card-item>
      </nb-card>
    </nb-content>
  </nb-container>
</template>

<script>
export default {
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    onPressRead() {
      this.navigation.navigate('ViewReflection')
    },
    onPressNav() {
      this.navigation.navigate('DrawerOpen');
    }
  }
}
</script>

