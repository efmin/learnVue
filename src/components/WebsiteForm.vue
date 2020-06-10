<template>
  <div id="website-form">
    <form @submit.prevent="handleSubmit">
      <label>Website name</label>
      <input v-model="website.name" type="text" />
      <label>Website URL</label>
      <input v-model="website.url" type="text" />
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
    methods: {
      handleSubmit(){
        this.$emit('add:website', this.website),
        console.log('inside handleSubmit')
      },
    },
  }
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>
