<template>
  <div @dateselect="dateselect"></div>
</template>

<script>
  import Calendar from 'sparrow-calendar'

  export default {
    props: ['date'],
    methods: {
      dateselect (e) {
        this.$emit('dateselect', e)
      }
    },
    mounted () {
      this.calendar = new Calendar({
        el: this.$el
      })
    }
  }
</script>

<style>
  .calendar {
    display: block;
    overflow: hidden;
    background: #fff;
    min-width: 320px;
    min-height: 272px;
  }
  .dropdown.calendar {
    min-width: 375px;
  }
  .calendar-header {
    padding: 15px;
    font-size: 24px;
    line-height: 30px;
    color: #ff9800;
    background: #f5f5f5;
  }
  .calendar-header > * {
    display: inline-block;
  }
  .calendar-header > .navi {
    float: right;
    font-size: 16px;
  }
  .calendar-header > .navi > a {
    margin-left: 10px;
  }
  .calendar-body {
    display: none;
    table-layout: fixed;
    width: 100%;
    min-height: 212px;
  }
  .calendar-body th {
    width: 1%;
    color: grey;
    font-size: 12px;
    font-weight: 600;
  }
  .calendar-body td,
  .calendar-body th {
    text-align: center;
    height: 28px;
    line-height: 20px;
    padding: 0 5px;
  }
  .calendar-body a {
    display: inline-block;
    border-radius: 10px;
    width: 100%;
  }
  .calendar-body a:active,
  html:not(.mobile) .calendar-body a:hover {
    background-color: #e0e0e0;
  }
  .calendar-body a.today {
    background-color: #ff9800;
    color: #fff;
  }
  .calendar-body a.active {
    background-color: #2196f3;
    color: #fff;
  }
</style>
