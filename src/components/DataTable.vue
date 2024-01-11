<template>
  <v-container fluid>
    <v-row>
      <v-card width="100%">
        <v-card-title>
          Data Table
        </v-card-title>
          <!-- <v-card-subtitle><p>Uh oh. There is nothing there. Using the data at <a href="https://random-data-api.com/">https://random-data-api.com/</a>, populate the table 
          below with headers and make it searchable. Also, expand the table to full width of the container. Let Bob know when complete.</p></v-card-subtitle> -->
        <v-data-table
          :headers="headers"
          :items="tableData"
          :items-per-page="10"
          :search="search"
          :loading="loading"
        >
          <template v-slot:top>
            <v-text-field
              v-model="search"
              label="Search"
              class="mx-4"
            ></v-text-field>
          </template>
        </v-data-table>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {

  data: () => {
    return {  
      tableData: [],
      headers: [
          { text: 'ID', value: 'id' },
          { text: 'UID', value: 'uid' },
          { text: 'Brand', value: 'brand' },
          { text: 'Name', value: 'name' },
          { text: 'Style', value: 'style' },
          { text: 'Hop', value: 'hop' },
          { text: 'Yeast', value: 'yeast' },
          { text: 'Malts', value: 'malts' },
          { text: 'IBU', value: 'ibu' },
          { text: 'Alcohol', value: 'alcohol' },
          { text: 'Blg', value: 'blg' },
      ],
      search: '',
      loading: true
    }
  },
  async mounted() {
    const response = await fetch("https://random-data-api.com/api/v2/beers?size=25")
    const data = await response.json()
    this.tableData = data
    this.loading = false
  }
};
</script>
