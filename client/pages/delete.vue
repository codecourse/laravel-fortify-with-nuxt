<template>
  <form @submit.prevent="deleteAccount">
    <button type="submit" class="bg-gray-400 py-1 px-3 rounded">Delete account</button>
  </form>
</template>

<script>
export default {
  methods: {
    async deleteAccount () {
      try {
        await this.$axios.delete('api/user')
        await this.$auth.logout()

        this.$router.replace({ name: 'index' })
      } catch (e) {
        //
      }
    }
  }
}
</script>