<template>
  <div id="website-form">
    <form @submit.prevent="handleSubmit">
      <label>Website name</label>
      <!-- keypress and focus to clearStatus resets the error messages
    to go away when user starts typing again -->
      <input
        ref="first"
        v-model="website.name"
        type="text"
        :class="{ 'has-error': submitting && invalidName }"
        @focus="clearStatus"
        @keypress="clearStatus"
         />
      <label>Website URL</label>
      <input
      v-model="website.url"
      type="text"
      :class="{ 'has-error': submitting && invalidUrl }"
      @focus="clearStatus"
       />
       <p v-if="error && submitting" class="error-message">
         Please fill out the required fields!
       </p>
       <p v-if="success" class="success-message">
         Employee successfully added
       </p>
      <button>Add Website</button>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'website-form',
    data() {
      return {
        // add a submitting state to check if the form is being submitted
        submitting: false,
        // add error state if something went wrong
        error: false,
        // add success state for if it goes through properly
        success: false,
        website: {
          name: '',
          url: '',
        },
      }
    },
    methods: {
      handleSubmit(){
        this.submitting = true
        // set submitting to true
        this.clearStatus()
        // call clearStatus method to clear the success and error status in
        // cause they have values set

        // check form validation, return error if either passes
        if (this.invalidName || this.invalidUrl) {
          this.error = true
          return
        }
        // fill website object with name and url, emit object
        this.$emit('add:website', this.website)
        // refocus the first input box upon submit
        this.$refs.first.focus()
        this.website = {
          name: '',
          url: '',
        }
        // reset all form state values
        this.error = false
        this.success = true
        this.submitting = false
      },

      clearStatus() {
        this.success = false
        this.error = false
      }
    },
    // computed properties are functions that are automatically
    // computed when something changes
    computed: {
      invalidName() {
        return this.website.name === ''
      },

      invalidUrl() {
        return this.website.url === ''
      },
    },
  }

</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }

  [class*='-message'] {
  font-weight: 500;
  }

  .error-message {
    color: #d33c40;
  }

  .success-message {
    color: #32a95d;
  }

</style>
