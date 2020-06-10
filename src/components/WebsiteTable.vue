<template>
  <div id="website-table">
    <table>
        <thead>
          <tr>
            <th>Website Name</th>
            <th>Website URL</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="website in websites" :key="website.id">
            <td>{{ website.name }}</td>
            <td>{{ website.url }}</td>
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
