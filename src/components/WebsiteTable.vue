<template>
  <div id="website-table">
    <p v-if="websites.length < 1" class="empty-table">
      No Websites Saved
    </p>
    <table v-else>
        <thead>
          <tr>
            <th>Website Name</th>
            <th>Website URL</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="website in websites" :key="website.id">
            <td v-if="editing === website.id">
              <input type="text" v-model="website.name" />
            </td>
            <td v-else>{{ website.name }}</td>
            <td v-if="editing === website.id">
              <input type="text" v-model="website.url" />
            </td>
            <td v-else>{{ website.url }}</td>
            <td v-if="editing === website.id">
            <td v-else>
              <button @click="editMode(website.id)" >Edit</button>
              <button @click="$emit('delete:website', website.id)">Delete</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
</template>

<script>
  export default {
    name: 'website-table',
    props: {
      websites: Array,
    },
    data() {
      return {
        editing: null,
      }
    },
    methods: {
      editMode(id) {
        this.editing = id
      },

      editWebsite(website) {
        if (website.name === '' || website.url === '') return
        this.$emit('edit:website', website.id, website)
        this.editing = null
      }
    }
  }
</script>

<style scoped>
  button {
    margin: 0 0.5rem 0 0;
  }
</style>
