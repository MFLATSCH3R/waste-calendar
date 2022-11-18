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
        <q-toolbar-title>{{ $t("MainLayoutHeader") }}</q-toolbar-title>
        <q-select
          color="white"
          bg-color="primary"
          v-model="locale"
          :options="localeOptions"
          filled
          borderless
          emit-value
          map-options
          options-dense
          style="min-width: 150px"
          >
          <template
            v-slot:option="scope"
            >
            <q-item v-bind="scope.itemProps" class="bg-primary">
              <q-item-section color="white">
                <q-item-label>{{ scope.opt.label }}</q-item-label>
              </q-item-section>
              <q-item-section avatar>
                <country-flag :country="scope.opt.countryIcon" size="small" />
              </q-item-section>
            </q-item>
          </template>
        </q-select>
      </q-toolbar>
    </q-header>
    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above="true"
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
import { useI18n } from 'vue-i18n'
import LocationCard from 'components/LocationCard.vue'
import CountryFlag from 'vue-country-flag-next'
export default {
  name: 'MainLayout',
  components: {
    LocationCard,
    CountryFlag
  },
  setup () {
    const { locale } = useI18n({ useScope: 'global' })
    return {
      locale,
      localeOptions: [
        { value: 'en-US', label: 'English', countryIcon: 'gb' },
        { value: 'de', label: 'German', countryIcon: 'de' }
      ]
    }
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
