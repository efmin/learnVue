<template>
  <div id="employee-form">
    <form>
      <label>Website name</label>
      <input type="text" />
      <label>Website Email</label>
      <input type="text" />
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
