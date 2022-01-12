<template>
  <div>
    <div class="np-clock-current-time np-home-font">
      {{ currentTime }}
    </div>
    <div class="np-author">Gautam Kabiraj</div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "ClockView",
  data() {
    return {
      currentTime: moment.utc(new Date()).local().format("hh:mm a"),
    };
  },
};
</script>

<style>
.np-home-font {
  color: #fff;
  font-size: 40px;
  padding-left: 30px;
  padding-top: 20px;
}
.np-author {
  padding-left: 30px;
  color: #fff;
  font-size: 12px;
}
</style>