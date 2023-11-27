<template>
  <div>
    Dashboard
  </div>
</template>

<script>
export default {
  middleware: ['auth', 'verified'],

  async mounted () {
    await this.$axios.get('api/dashboard')
  }
}
</script>