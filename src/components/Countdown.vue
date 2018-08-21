<template>
  <div class="timer">
      <div class="block">
          <p class="digit">{{ days | twoDigits }}</p>
          <p class="text">Days</p>
      </div>
      <div class="block">
          <p class="digit">{{ hours | twoDigits }}</p>
          <p class="text">Hours</p>
      </div>
      <div class="block">
          <p class="digit">{{ minutes | twoDigits }}</p>
          <p class="text">Minutes</p>
      </div>
      <div class="block">
          <p class="digit">{{ seconds | twoDigits }}</p>
          <p class="text">Seconds</p>
      </div>
  </div>
</template>
<script>
import moment from 'moment'

export default {
  name: 'countdown',
  props: {
    propDate: String
  },
  data () {
    return {
      now: moment(),
      date: moment(this.propDate)
    }
  },
  created () {
    window.setInterval(() => {
      this.now = moment()
    }, 1000)
  },
  computed: {
    seconds () {
      return this.date.diff(this.now, 'seconds') % 60
    },
    minutes () {
      return this.date.diff(this.nowl, 'minutes') % 60
    },

    hours () {
      return this.date.diff(this.now, 'hours') % 24
    },

    days () {
      return Math.trunc(moment.duration(this.date.diff(this.now)).as('days'))
    }
  },
  filters: {
    twoDigits (value) {
      if (value.toString().length <= 1) {
        return '0' + value.toString()
      }
      return value.toString()
    }
  }
}
</script>

<style scoped lang="scss">
@import url(https://fonts.googleapis.com/css?family=Roboto+Condensed:400|Roboto:100);

.block {
    display: flex;
    flex-direction: column;
    margin: 20px;
}

.text {
    color: #1abc9c;
    font-size: 40px;
    font-family: 'Roboto Condensed', serif;
    font-weight: 40;
    margin-top:10px;
    margin-bottom: 10px;
    text-align: center;
}

.digit {
    color: #ecf0f1;
    font-size: 150px;
    font-weight: 100;
    font-family: 'Roboto', serif;
    margin: 10px;
    text-align: center;
}

.timer {
    align-items: center;
    bottom: 0;
    background-color: transparent;
    display: flex;
    justify-content: center;
    left: 0;
    position: absolute;
    right: 0;
    top:0;
    z-index: 3;
}
</style>
