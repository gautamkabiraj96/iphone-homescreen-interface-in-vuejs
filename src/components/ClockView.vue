<template>
  <div class="np-app-container">
    <div class="np-app-title">Clock</div>
    <div class="np-clock-current-time">
      {{ currentTime }}
    </div>
    <div>
      {{ getDayOfTheWeek(currentDay) }}
    </div>
    <div class="np-current-date">
      {{ currentDate }}
    </div>
    <div class="np-credit">www.nightprogrammer.com</div>
    <div>
      <img class="np-clock-img" src="https://picsum.photos/210/240" />
    </div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "ClockView",
  data() {
    return {
      currentTime: moment.utc(new Date()).local().format("hh:mm:a"),
      currentDate: moment.utc(new Date()).local().format("MM/DD/YYYY"),
      currentDay: moment.utc(new Date()).local().day(),
    };
  },
  methods: {
    getDayOfTheWeek(currentDay) {
      switch (currentDay) {
        case 1:
          return "Monday";
        case 2:
          return "Tuesday";
        case 3:
          return "Wednesday";
        case 4:
          return "Thursday";
        case 5:
          return "Friday";
        case 6:
          return "Saturday";
        case 7:
          return "Sunday";
        default:
          return "Good day";
      }
    },
  },
};
</script>

<style>
.np-clock-current-time {
  font-size: 30px;
  margin-top: 10px;
}
.np-current-date {
  padding-top: 10px;
}
.np-clock-img {
  border-radius: 4px;
  margin-top: 15px;
}
.np-credit {
  font-size: 12px;
}
</style>