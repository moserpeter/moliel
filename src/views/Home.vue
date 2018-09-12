<template>
  <div class="home">
    <overlay opacity="0.8">

    </overlay>
    <countdown propDate="September 31, 2018"></countdown>
  </div>
</template>

<script>
// @ is an alias to /src
import Overlay from '@/components/Overlay'
import Countdown from '@/components/Countdown'

export default {
  name: 'home',
  components: {
    Overlay,
    Countdown
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

html, body {
    height:99%;
}

body {
  background-image: url('../assets/background.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: left top;
}
</style>
