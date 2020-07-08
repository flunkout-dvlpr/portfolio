<template>
  <q-tabs
    v-model="tab"
    inline-label
    class="bg-accent text-black shadow-2"
  >
  <q-tab
    v-for="tab in tabs"
    :key="tab.id"
    :name="tab.id"
    :icon="tab.icon"
    :label="tab.label"
  />
  </q-tabs>

</template>

<script>
export default {
  data () {
    return {
      tab: 1,
      tabs: [
        {
          id: 1,
          label: 'Code',
          icon: 'integration_instructions'
        },
        {
          id: 2,
          label: 'Life',
          icon: 'person_pin'
        },
        {
          id: 3,
          label: 'Books',
          icon: 'book'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
