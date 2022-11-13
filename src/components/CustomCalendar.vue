<template>
  <calendar
      is-dark
      is-expanded
      trim-weeks
      :attributes="todos"
      :columns="layout.col"
      :rows="layout.rows"
      locale="de"
      >
      <template #day-popover="{ dayTitle, attributes }">
        <div>
          <div class="text-xs text-gray-300 font-semibold text-center">
            {{ dayTitle }}
          </div>
          <ul>
            <li v-for="attr in attributes" :key="attr.key" :attribute="attr">
              {{ attr.customData.description }}
            </li>
          </ul>
        </div>
      </template>
    </calendar>
</template>

<script>
import 'v-calendar/dist/style.css'
import { Calendar } from 'v-calendar'
export default {
  name: 'CustomCalendar',
  components: {
    Calendar
  },
  props: {
    todos: Array
  },
  computed: {
    layout () {
      return this.$q.screen.lt.md ? { col: 1, rows: 1 } : { col: 2, rows: 1 }
    },
    attrs () {
      return [
        ...this.todos.map(todo => ({
          dates: todo.dates,
          dot: {
            color: todo.color
          },
          popover: {
            label: todo.description
          },
          customData: todo
        }))
      ]
    }
  }
}
</script>

<style scoped lang="css">
.bg-page {
  background: #0F2027;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to top, #2C5364, #203A43, #0F2027);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to top, #2C5364, #203A43, #0F2027); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>
