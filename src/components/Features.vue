<template lang="">
  <div class="features">
    <div>
      <h5 class="d-inline-block">Features:</h5>
      <Badge class="ms-2 mt-2" v-for="badgeText in badgeList">{{ badgeText }}</Badge>
    </div>
    <p class="pt-3">This line of text is meant to be treated as fine print.</p>
  </div>
</template>
<script>
import Badge from './Badge.vue'
export default {
  name: 'Features',
  components: {
    Badge
  },
  data() {
    return {
      badgeList: [
        'Free domain protection when you add hosting',
        'Free site builder',
        'Management portal',
        '24/7 support'
      ]
    }
  }
}
</script>
<style lang="scss"></style>
