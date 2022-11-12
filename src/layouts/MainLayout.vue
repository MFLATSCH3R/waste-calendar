<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          />
        <q-toolbar-title>Müllkalender Waidring</q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      side="left"
      bordered
      >
      <q-list>
        <q-item-label header>
          Standorte
        </q-item-label>
        <LocationCard
          v-for="location in locations"
          :key="location.key"
          :label="location.label"
          :address="location.address"
          :openingHours="location.openingHours"
        />
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import LocationCard from 'components/LocationCard.vue'
export default {
  name: 'MainLayout',
  components: {
    LocationCard
  },
  data () {
    return {
      leftDrawerOpen: false,
      locations: [
        {
          key: 1,
          label: 'Gemeindeamt',
          address: {
            street: 'Dorfstraße',
            number: '9',
            postcode: '6384',
            city: 'Waidring'
          }
        },
        {
          key: 2,
          label: 'Recyclinghof',
          address: {
            street: 'Dorfstraße',
            number: '9',
            postcode: '6384',
            city: 'Waidring'
          }
        },
        {
          key: 3,
          label: 'Abwasserverband Waidring-St. Ulrich a. P.',
          address: {
            street: 'Hausstattweg',
            number: '1A',
            postcode: '6384',
            city: 'Waidring'
          }
        }
      ]
    }
  },
  methods: {
    toggleLeftDrawer () {
      this.leftDrawerOpen = !this.leftDrawerOpen
    }
  }
}
</script>
