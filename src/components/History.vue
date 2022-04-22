<template>
  <div class="history">
    <h1>История</h1>
    <p>
      Устойчивая стратегия роста, концентрация на основных компетенциях и
      клиентоориентированность — ключевые факторы успеха на рынке
      металлопродукции в течение 17 лет.
    </p>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'History'
})
</script>

<style scoped lang="scss">
.history {
  flex-grow: 1;
  margin: 292px 377px 89px 137px;
}
h1,
p {
  font-weight: 600;
}
h1 {
  font-size: 46px;
  line-height: 48px;
  margin-bottom: 30px;
}
p {
  width: 664px;
  font-size: 16px;
  line-height: 24px;
}
@media (max-width: 768px) {
  .history {
    margin: 202px 77px 83px 78px;
  }
  p {
    width: 613px;
  }
}
@media (max-width: 576px) {
  .history {
    margin: 183px 18px 43px 16px;
  }
  p {
    width: 341px;
  }
}
</style>
