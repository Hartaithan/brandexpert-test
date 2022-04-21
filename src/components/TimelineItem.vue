<template>
  <div class="timeline-item">
    <div class="timeline-item__content">
      <p class="timeline-item__year">{{ item.year }}</p>
      <p class="timeline-item__title">{{ item.title }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { ITimelineItem } from '../models/timelineModel'

export default Vue.extend({
  name: 'TimelineItem',
  props: {
    item: {
      required: true,
      type: Object as () => ITimelineItem
    }
  }
})
</script>

<style scoped lang="scss">
.timeline-item {
  &__content,
  &__title {
    font-weight: 600;
  }
  &__content {
    font-size: 36px;
    line-height: 40px;
  }
  &__title {
    font-size: 16px;
    line-height: 24px;
  }
}
</style>
