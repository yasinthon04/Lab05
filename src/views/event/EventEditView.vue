<template>
  <p>Edit form here</p>
  <button @click="edit">Edit here</button>
</template>

<script>
export default {
  props: ['id', 'event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.GStore.flashMessage =
        'You are successfully edit for ' + this.event.title
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)
      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
