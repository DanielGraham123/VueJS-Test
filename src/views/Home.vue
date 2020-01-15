<template>
  <div class="home">
    
    <v-container>

      <v-row >

        <v-col v-for="(item, index) in items[0]" :key="index" class="col-md-4 col-lg-3 col-sm-6">
          <v-card class="mx-auto" max-width="400" >
            <v-img class="white--text align-end" height="200px" :src=" item.url">
              <v-card-title class="text-capitalize">{{ item.title }}</v-card-title>
            </v-img>

            <v-card-subtitle class="pb-0">Article {{ index+1 }}</v-card-subtitle>

            <v-card-text class="text--primary">

              <div>{{item.title}}</div>

              <a>{{item.thumbnailUrl}}</a>
            </v-card-text>

            <v-card-actions>
              <v-btn color="blue" text>
                View
              </v-btn>

              <v-btn color="blue" text>
                Share
              </v-btn>

            </v-card-actions>
          </v-card>
        </v-col>

      </v-row>

    </v-container>
  
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'home',
  components: {

  },
  data() {
    return {
      items: []
    }
  },

  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/photos').then(response => (this.items.push(response.data.slice(1, 15))))

  },

  created () {
    this.items.slice(1, 15)

    console.log(this.items)
  }
  
}
</script>
