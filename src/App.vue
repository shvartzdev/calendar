<template>
  <div id="app">
    <CalendarWeek />
    <CalendarEntry />
    <CustomEvents />
  </div>
</template>

<script>
import CalendarWeek from './components/CalendarWeek.vue';
import CalendarEntry from './components/CalendarEntry.vue';
import CustomEvents from './components/CustomEvents.vue';

export default {
  name: 'App',
  components: {
    CalendarWeek,
    CalendarEntry,
    CustomEvents
  }
}
</script>

<style lang="scss">
html, body {
  height: 100%;
}
</style>

<style lang="scss" scoped>
#app {
  height: inherit;
  background: #6e6e6e;
  display: flex;
  flex-direction: column;
  align-items: center;
  -webkit-align-items: center;
  justify-content: center;
  -webkit-justify-content: center;
}
</style>
