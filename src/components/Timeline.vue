<template>
  <div class="timeline">
    <TimelineItem v-for="item in items" :key="item.message" :item="item" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { ITimelineItem } from '../models/timelineModel'
import TimelineItem from './TimelineItem.vue'

export default Vue.extend({
  components: { TimelineItem },
  name: 'Timeline',
  data (): {
    items: ITimelineItem[];
    } {
    return {
      items: [
        {
          id: 1,
          year: 2003,
          title: 'Основание предприятия по торговле чёрным металлопрокатом'
        },
        {
          id: 2,
          year: 2008,
          title: 'Включение в ассортимент цветных металлов и нержавейки'
        },
        {
          id: 3,
          year: 2013,
          title: 'Открытие подразделения по металлообработке'
        },
        {
          id: 4,
          year: 2020,
          title:
            'Открытие собственного завода по обработке металлов и производству металлоконструкций'
        }
      ]
    }
  }
})
</script>

<style scoped lang="scss">
.timeline {
  display: flex;
  flex-direction: row;
}
</style>
