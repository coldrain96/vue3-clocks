<template>
  <div class="vertical-middle bg-gradient">
    <div class="vertical-middle__child">

      <div class="clock">
        <ul class="clock__marks"></ul>
        <div class="clock__hands">
          <div class="clock__hand clock__hand--hour"></div>
          <div class="clock__hand clock__hand--minute"></div>
          <div class="clock__hand clock__hand--second"></div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
  import { ref } from 'vue'
  export default {
    setup () {
      let currentDatetime = new Date()
      let time = ref({
        hours: currentDatetime.getHours(),
        minutes: currentDatetime.getMinutes(),
        seconds: currentDatetime.getSeconds(),
        milliseconds: currentDatetime.getMilliseconds(),
      })

      return {
        time
      }
    }
  }
  // var radius = 6;
  //
  // $(document).ready(function() {
  //   for(var i=0; i<60; i++)
  //     $('.clock__marks').append('<li></li>');
  //
  //   var currentTime = new Date();
  //   var second = currentTime.getSeconds() * radius;
  //   var minute = currentTime.getMinutes() * radius + Math.floor(second / (radius * 10) * 10) / 10;
  //   var hour = currentTime.getHours() * radius * 5 + Math.floor(minute / (radius * 2) * 10) / 10;
  //
  //   setClockHands(second, minute, hour);
  // });
  //
  // function setClockHands(second, minute, hour){
  //   var secondElm = $('.clock__hand--second');
  //   var minuteElm = $('.clock__hand--minute');
  //   var hourElm = $('.clock__hand--hour');
  //
  //   secondElm.css('transform', 'rotate(' + second + 'deg)');
  //   minuteElm.css('transform', 'rotate(' + minute + 'deg)');
  //   hourElm.css('transform', 'rotate(' + hour + 'deg)');
  //
  //   var interval = 1000; //1 second
  //   var before = new Date();
  //
  //   setInterval(function(){
  //     var now = new Date();
  //     var elapsedTime = now.getTime() - before.getTime(); //Fix calculating in inactive tabs
  //     var delay = Math.round(elapsedTime/interval);
  //
  //     second += radius * delay;
  //     for(var i=0; i<delay; i++){
  //       if( ((second - i) * radius) % (radius * 5) === 0 ){
  //         minute += 0.5;
  //         if( minute % radius === 0 ){
  //           hour += 0.5;
  //         }
  //       }
  //     }
  //
  //     secondElm.css('transform', 'rotate(' + second + 'deg)');
  //     minuteElm.css('transform', 'rotate(' + minute + 'deg)');
  //     hourElm.css('transform', 'rotate(' + hour + 'deg)');
  //
  //     before = new Date();
  //   }, interval);
  // }
</script>

<style src="@/assets/clocks.scss" lang="scss" scoped></style>
