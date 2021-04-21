<template>
  <!-- SIDE BAR SECTIION -->
  <q-item
    clickable
    tag="a"
    target="_blank"
    :href="link"
  >
    <!-- SIDE BAR ICONS -->
    <q-item-section
      v-if="icon"
      avatar
    >
      <q-icon :name="icon" />
    </q-item-section>

    <!-- SIDE BAR MENU TITLE -->
    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
export default {
  name: 'EssentialLink',
  props: {
    title: {
      type: String,
      required: true
    },

    caption: {
      type: String,
      default: ''
    },

    link: {
      type: String,
      default: '#'
    },

    icon: {
      type: String,
      default: ''
    }
  }
}
</script>
