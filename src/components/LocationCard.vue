<template>
  <q-card class="q-mb-md">
    <q-card-section class="bg-primary text-white">
      <div class="text-h6">{{ label }}</div>
      <div class="text-subtitle2">{{ address.street }} {{ address.number }}</div>
      <div class="text-subtitle2">{{ address.postcode}} {{ address.city }}</div>
    </q-card-section>
    <q-card-section class="q-pt-none">
      <span>Öffnungszeiten:</span>
    </q-card-section>
  </q-card>
</template>

<script>
export default {
  name: 'LocationCard',
  props: {
    label: null,
    address: {
      street: null,
      number: null,
      postcode: null,
      city: null
    },
    openingHours: null
  }
}
</script>
