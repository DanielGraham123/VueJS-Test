<template>
    <div class="items">
        <v-ul>
            <v-li hoverable v-for="(item, index) in items[0]" :key="index">
                <v-card class=" ">
                    <v-container fluid>
                        <v-row>
                            <v-col class="col-2">
                                <v-img aspect-ratio width="50px" height="50px" :src="item.url" alt="image" class="img-fluid"/>
                            </v-col>    
                            <v-col class="col-10">
                                <span class="name">
                                    {{ item.title }}
                                </span>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-li>
        </v-ul>
    </div>
</template>


<script>
import axios from 'axios'



export default {
    name: "items",

    data() {
        return {
            items: [],
            baseURL: process.env.VUE_APP_BASE_URL,
        }
    },

    methods: {
        fetchData() {
            axios.get("https://jsonplaceholder.typicode.com/photos/").then(response => (
                // console.log(response.data);
                this.items.push(response.data.slice(1, 10))
            ))
        }
    },

    created() {
        this.fetchData()
        // this.items.slice(1, 10)
        console.log(this.items)
    }
    
}
</script>