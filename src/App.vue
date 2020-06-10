<template>
  <div id="app" class="small-container">
    <h1>Websites</h1>

    <website-table :websites="websites" />
  </div>
</template>


<script>
import WebsiteTable from '@/components/WebsiteTable.vue'

export default {
  name: 'App',
  components: {
    WebsiteTable
  },
  data() {
    return {
      websites: [
        {
          id: 1,
          name: 'New York Times',
          url: 'https://www.nytimes.com'
        },
        {
          id: 2,
          name: 'Financial Times',
          url: 'https://www.ft.com'
        },
        {
          id: 3,
          name: 'Aljazeera',
          url: 'https://www.aljazeera.com'
        },
      ],
    }
  },
}
</script>


<style>
  button {
    background: #009435;
    border: 1px solid #009435
  }

  .small-countainer {
    max-width: 680px;
  }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
