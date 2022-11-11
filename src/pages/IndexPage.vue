<template>
  <q-page class="flex flex-center">
    <WeekDateType />
  </q-page>
</template>

<script>
import WeekDateType from 'components/CalendarWeek.vue'
export default {
  name: 'IndexPage',
  components: {
    WeekDateType
  }
}
</script>
