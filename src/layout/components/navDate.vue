<template>
  <div class="nav-date">
    <span>{{timers.hour}}</span> :
    <span>{{timers.minute}}</span> :
    <span style="margin-right: 5px;">{{timers.second}}</span>  
    星期{{timers.week}}
  </div>
</template>
<script>
import { dateFormat } from '@/utils/format'
export default {
  data() {
    return {
      timers: {
        timer: null,
        month: '01',
        day: '01',
        hour: '00',
        minute: '00',
        second: '00',
        week: '一'
      }
    }
  },
  mounted() {
    dateFormat(this)
  },
  destroyed() {
    this.timers.timer = null
  }
}
</script>
<style lang="scss" scoped>
  .nav-date {
    font-size: 16px;
    font-weight: 500;
    span {
      display: inline-block;
      letter-spacing: 2px;
      color: #fff;
      padding: 0 13px;
      background: $default-color;
    }
  }
</style>