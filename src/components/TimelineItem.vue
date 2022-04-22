<template>
  <div class="timeline-item">
    <div class="timeline-item__content">
      <p class="timeline-item__year">{{ item.year }}</p>
      <p class="timeline-item__title">{{ item.title }}</p>
    </div>
    <div class="timeline-item__point" />
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
  position: relative;
  display: flex;
  align-self: flex-end;
  height: 100px;
  width: 360px;
  &:nth-child(odd) {
    align-self: flex-start;
    & > .timeline-item__point {
      top: unset;
      bottom: -48px;
    }
  }
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
  &__point {
    position: absolute;
    border-radius: 50%;
    background: #ff6b00;
    height: 16px;
    width: 16px;
    top: -48px;
    bottom: unset;
  }
}
@media (max-width: 768px) {
  .timeline-item {
    height: 170px;
    width: 183px;
  }
}
@media (max-width: 576px) {
  .timeline-item {
    height: 110px;
    width: 344px;
  }
}
</style>
