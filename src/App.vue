<template>
  <div id="app" class="small-container">
    <h1>Websites</h1>

    <website-form @add:website="addWebsite" />

    <website-table
      :websites="websites"
      @delete:website="deleteWebsite"
      @edit:website="editWebsite"
    />
  </div>
</template>


<script>
import WebsiteTable from '@/components/WebsiteTable.vue'
import WebsiteForm from '@/components/WebsiteForm.vue'

export default {
  name: 'App',
  components: {
    WebsiteTable,
    WebsiteForm,
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
  methods: {
    addWebsite(website){
      console.log("inside addWebsite");
      const lastId =
        this.websites.length > 0
        ? this.websites[this.websites.length - 1].id
        : 0;
      const id = lastId + 1;
      const newWebsite = { ...website, id };

      this.websites = [...this.websites, newWebsite];
    },
    deleteWebsite(id) {
      this.website = this.website.filter(
        website => website.id != id
      )
    },
    editWebsite(id, updatedWebsite) {
      this.websites = this.websites.map(website =>
        website.id === id ? updatedWebsite : website 
      )
    }
  }
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
