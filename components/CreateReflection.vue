<template>
  <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent :on-press="() => navigation.goBack()">
          <nb-icon :name="'arrow-back'" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Create A Reflection</nb-title>
      </nb-body>
      <nb-right/>
    </nb-header>
    <nb-content>
      <nb-form>
        <nb-item stackedLabel>
          <nb-label>Today's Success</nb-label>
          <nb-textarea class="reflection-text-area" :rowSpan="3" bordered placeholder="Success" />
        </nb-item>
        <nb-item stackedLabel>
          <nb-label>Today's Low Point</nb-label>
          <nb-textarea class="reflection-text-area" :rowSpan="3" bordered placeholder="Low Point" />
        </nb-item>
        <nb-item stackedLabel>
          <nb-label>Improvement Plan</nb-label>
          <nb-textarea class="reflection-text-area" :rowSpan="3" bordered placeholder="Improvement Plan"/>
        </nb-item>
      </nb-form>
      <nb-button full>
        <nb-text>Create</nb-text>
      </nb-button>
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

<style scoped>
  .reflection-text-area {
    width: 100%
  }
</style>
