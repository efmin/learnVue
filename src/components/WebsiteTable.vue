<template>
  <div id="website-table">
    <table>
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
              <button>Edit</button>
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

<style scoped></style>
