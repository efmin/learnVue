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
          <tr>
            <td>New York Times</td>
            <td>https://www.nytimes.com</td>
          </tr>
          <tr>
            <td>Financial Times</td>
            <td>https://www.ft.com</td>
          </tr>
          <tr>
            <td>Aljazeera</td>
            <td>https://www.aljazeera.com</td>
          </tr>
        </tbody>
      </table>
    </div>
</template>

<script>
  export default {
    name: 'website-table',
    props: {
      website: Array,
    },
  }
</script>

<style scoped></style>
