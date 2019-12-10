<template>
  <div class="hello">
    <vue-hash-calendar
      ref="picker"
      model="inline"
      :scroll-change-date="true"
      :visible.sync="isShowCalendar"
      :default-datetime="defaultDatetime"
      :showTodayButton="false"
      format="YY/MM/DD"
      week-start="sunday"
      picker-type="date"
      @click="dateClick"
      @slidechange="changeSlide"
      @change="dateChange">
    </vue-hash-calendar>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      isShowCalendar: true,//是否显示弹窗
      isShowTips: false,//是否显示下载提示
      defaultDatetime: new Date(),
    }
  },
  methods: {
    dateChange(date) {// 日期改变触发
      console.log(date,'change');
    },
    dateClick(date) {// 点击日期时按钮触发
      console.log(date,'click');
    },
    changeSlide(direction) {
      console.log(direction)
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hello >>> .calendar_content {
    height: 100% !important;
    padding-bottom: 0;
  }
  .hello >>> .calendar_title_date {
    width: 100%;
    text-align: center;
  }
</style>
