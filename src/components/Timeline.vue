<template>
  <div class="timeline">
    <div
      class="timeline__wrapper"
      :style="'transform: translateX(' + translate + 'px)'"
    >
      <TimelineItem v-for="item in items" :key="item.message" :item="item" />
    </div>
    <div class="timeline__arrows">
      <svg
        class="timeline__arrows__left"
        width="48"
        height="48"
        viewBox="0 0 48 48"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        v-on:click="left"
      >
        <circle cx="24" cy="24" r="23.5" stroke="white" />
        <g clip-path="url(#clip0_228_135)">
          <path
            d="M21.707 29.8821L27.795 23.7941L21.707 17.7071"
            stroke="white"
            stroke-width="2"
          />
        </g>
        <defs>
          <clipPath id="clip0_228_135">
            <rect
              width="8.209"
              height="13.589"
              fill="white"
              transform="translate(21 17)"
            />
          </clipPath>
        </defs>
      </svg>
      <svg
        class="timeline__arrows__right"
        width="48"
        height="48"
        viewBox="0 0 48 48"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        v-on:click="right"
      >
        <circle cx="24" cy="24" r="23.5" stroke="white" />
        <g clip-path="url(#clip0_228_135)">
          <path
            d="M21.707 29.8821L27.795 23.7941L21.707 17.7071"
            stroke="white"
            stroke-width="2"
          />
        </g>
        <defs>
          <clipPath id="clip0_228_135">
            <rect
              width="8.209"
              height="13.589"
              fill="white"
              transform="translate(21 17)"
            />
          </clipPath>
        </defs>
      </svg>
    </div>
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
    translate: number;
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
      ],
      translate: 0
    }
  },
  methods: {
    left: function () {
      if (this.translate < 0) {
        this.translate = this.translate + 360
      }
    },
    right: function () {
      if (this.translate > -((this.items.length - 2) * 360)) {
        this.translate = this.translate - 360
      }
    }
  }
})
</script>

<style scoped lang="scss">
.timeline {
  width: 100vw;
  height: 280px;
  position: relative;
  overflow: hidden;
  &__wrapper {
    transform: translateX(0px);
    transition: 0.5s transform ease-in-out;
    width: fit-content;
    height: 100%;
    display: flex;
    flex-direction: row;
    margin-left: 137px;
  }
  &__arrows {
    width: 100%;
    position: fixed;
    bottom: 88px;
    padding: 0 137px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    &__left,
    &__right {
      cursor: pointer;
    }
    &__left {
      transform: rotate(180deg);
    }
  }
  &::after {
    background: #ff6b00;
    content: '';
    position: absolute;
    top: calc(50% - 0.5px);
    height: 1px;
    width: 200vw;
  }
}
</style>
