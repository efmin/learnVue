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
            <td>{{ website.name }}</td>
            <td>{{ website.url }}</td>
            <td>
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
  }
</script>

<style scoped>
  button {
    margin: 0 0.5rem 0 0;
  }
</style>
