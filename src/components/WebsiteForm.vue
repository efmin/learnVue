<template>
  <div id="employee-form">
    <form>
      <label>Website name</label>
      <input type="text" v-model="website.name"/>
      <label>Website URL</label>
      <input type="text" v-model="website.url" />
      <button>Add Website</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'website-form',
    data() {
      return {
        website: {
          name: '',
          url: '',
        },
      }
    },
  }
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>
