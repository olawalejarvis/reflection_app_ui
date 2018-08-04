<template>
  <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent :on-press="() => navigation.goBack()">
          <nb-icon :name="'arrow-back'" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Reflection</nb-title>
      </nb-body>
      <nb-right/>
    </nb-header>

    <nb-content padder>
      <nb-h1> 12 July, 2018 Reflection </nb-h1>
      
      <nb-card transparent>
        <nb-card-item header bordered>
          <nb-text>Success</nb-text>
        </nb-card-item>
        <nb-card-item bordered>
          <nb-body>
            <nb-text>
              NativeBase is a free and open source framework that enable developers to build high-quality mobile apps using React Native iOS and Android apps with a fusion of ES6.
            </nb-text>
          </nb-body>            
        </nb-card-item>

        <nb-card-item header bordered>
          <nb-text>Low Point</nb-text>
        </nb-card-item>
        <nb-card-item bordered>
          <nb-body>
            <nb-text>
              NativeBase is a free and open source framework that enable developers to build high-quality mobile apps using React Native iOS and Android apps with a fusion of ES6.
            </nb-text>
          </nb-body>            
        </nb-card-item>

        <nb-card-item header bordered>
          <nb-text>Improvement Plan</nb-text>
        </nb-card-item>
        <nb-card-item bordered>
          <nb-body>
            <nb-text>
              NativeBase is a free and open source framework that enable developers to build high-quality mobile apps using React Native iOS and Android apps with a fusion of ES6.
            </nb-text>
          </nb-body>            
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
  }
}
</script>
