<template>
  <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent :on-press="() => navigation.goBack()">
          <nb-icon :name="'arrow-back'" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Feedback</nb-title>
      </nb-body>
      <nb-right/>
    </nb-header>
    <nb-content>
      <nb-form>
        <nb-item>
          <nb-input placeholder="Name" />
        </nb-item>
        <nb-item last>
          <nb-textarea class="reflection-text-area" placeholder="Feedback" />
        </nb-item>
      </nb-form>
      <nb-button full>
        <nb-text>Submit</nb-text>
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
