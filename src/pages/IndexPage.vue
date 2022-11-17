<template>
  <q-page class="flex flex-center bg-page">
    <custom-calendar :todos="attrs" />
  </q-page>
</template>

<script>
import moment from 'moment'
import CustomCalendar from 'src/components/CustomCalendar.vue'
export default {
  name: 'IndexPage',
  components: {
    CustomCalendar
  },
  data () {
    return {
      attrs: [
        {
          key: 0,
          highlight: false,
          dot: 'blue',
          bar: false,
          content: 'red',
          dates: [
            new Date(moment('07.11.2022', 'DD.MM.YYYY')),
            new Date(moment('14.11.2022', 'DD.MM.YYYY')),
            new Date(moment('21.11.2022', 'DD.MM.YYYY')),
            new Date(moment('28.11.2022', 'DD.MM.YYYY')),
            new Date(moment('05.12.2022', 'DD.MM.YYYY')),
            new Date(moment('12.12.2022', 'DD.MM.YYYY')),
            new Date(moment('19.12.2022', 'DD.MM.YYYY')),
            new Date(moment('27.12.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Recyclinghof (MO)'
          }
        },
        {
          key: 1,
          highlight: false,
          dot: 'blue',
          bar: false,
          content: 'red',
          dates: [
            new Date(moment('04.11.2022', 'DD.MM.YYYY')),
            new Date(moment('11.11.2022', 'DD.MM.YYYY')),
            new Date(moment('18.11.2022', 'DD.MM.YYYY')),
            new Date(moment('25.11.2022', 'DD.MM.YYYY')),
            new Date(moment('02.12.2022', 'DD.MM.YYYY')),
            new Date(moment('09.12.2022', 'DD.MM.YYYY')),
            new Date(moment('16.12.2022', 'DD.MM.YYYY')),
            new Date(moment('23.12.2022', 'DD.MM.YYYY')),
            new Date(moment('30.12.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Recyclinghof (FR)'
          }
        },
        {
          key: 2,
          highlight: false,
          dot: 'orange',
          bar: false,
          content: 'red',
          dates: [
            new Date(moment('29.12.2021', 'DD.MM.YYYY')),
            new Date(moment('12.01.2022', 'DD.MM.YYYY')),
            new Date(moment('26.01.2022', 'DD.MM.YYYY')),
            new Date(moment('09.02.2022', 'DD.MM.YYYY')),
            new Date(moment('23.02.2022', 'DD.MM.YYYY')),
            new Date(moment('09.03.2022', 'DD.MM.YYYY')),
            new Date(moment('23.03.2022', 'DD.MM.YYYY')),
            new Date(moment('06.04.2022', 'DD.MM.YYYY')),
            new Date(moment('20.04.2022', 'DD.MM.YYYY')),
            new Date(moment('04.05.2022', 'DD.MM.YYYY')),
            new Date(moment('18.05.2022', 'DD.MM.YYYY')),
            new Date(moment('01.06.2022', 'DD.MM.YYYY')),
            new Date(moment('15.06.2022', 'DD.MM.YYYY')),
            new Date(moment('29.06.2022', 'DD.MM.YYYY')),
            new Date(moment('13.07.2022', 'DD.MM.YYYY')),
            new Date(moment('27.07.2022', 'DD.MM.YYYY')),
            new Date(moment('10.08.2022', 'DD.MM.YYYY')),
            new Date(moment('24.08.2022', 'DD.MM.YYYY')),
            new Date(moment('07.09.2022', 'DD.MM.YYYY')),
            new Date(moment('21.09.2022', 'DD.MM.YYYY')),
            new Date(moment('05.10.2022', 'DD.MM.YYYY')),
            new Date(moment('19.10.2022', 'DD.MM.YYYY')),
            new Date(moment('02.11.2022', 'DD.MM.YYYY')),
            new Date(moment('16.11.2022', 'DD.MM.YYYY')),
            new Date(moment('30.11.2022', 'DD.MM.YYYY')),
            new Date(moment('14.12.2022', 'DD.MM.YYYY')),
            new Date(moment('28.12.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Restmüll'
          }
        },
        {
          key: 3,
          highlight: false,
          dot: 'yellow',
          bar: false,
          content: 'orange',
          dates: [
            new Date(moment('08.01.2022', 'DD.MM.YYYY')),
            new Date(moment('03.02.2022', 'DD.MM.YYYY')),
            new Date(moment('03.03.2022', 'DD.MM.YYYY')),
            new Date(moment('07.04.2022', 'DD.MM.YYYY')),
            new Date(moment('05.05.2022', 'DD.MM.YYYY')),
            new Date(moment('02.06.2022', 'DD.MM.YYYY')),
            new Date(moment('07.07.2022', 'DD.MM.YYYY')),
            new Date(moment('04.08.2022', 'DD.MM.YYYY')),
            new Date(moment('01.09.2022', 'DD.MM.YYYY')),
            new Date(moment('06.10.2022', 'DD.MM.YYYY')),
            new Date(moment('03.11.2022', 'DD.MM.YYYY')),
            new Date(moment('01.12.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Gelber Sack'
          }
        },
        {
          key: 4,
          highlight: false,
          dot: 'green',
          bar: false,
          content: 'red',
          dates: [
            new Date(moment('08.01.2022', 'DD.MM.YYYY')),
            new Date(moment('05.02.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Christbaum Entsorgung'
          }
        },
        {
          key: 5,
          highlight: false,
          dot: 'red',
          bar: false,
          content: 'red',
          dates: [
            new Date(moment('29.04.2022', 'DD.MM.YYYY')),
            new Date(moment('23.09.2022', 'DD.MM.YYYY'))
          ],
          excludedDates: null,
          order: 0,
          popover: true,
          customData: {
            description: 'Problemstoffe'
          }
        }
      ]
    }
  }
}
</script>

<style scoped lang="css">
.bg-page {
  background: #0F2027;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to bottom, #2C5364, #203A43, #0F2027);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to bottom, #2C5364, #203A43, #0F2027); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>
