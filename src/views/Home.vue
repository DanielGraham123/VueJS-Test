<template>
  <div class="home">
    
    <v-container class="py-5">
      <v-row class="d-flex justify-center my-5 py-5">

        <v-col class="ma-5 pa-5 d-flex justify-center">
          <v-btn @click="clickedColor('green')" height=70px class="display-1 green white--text font-weight-bold">click me</v-btn>
    
        </v-col>

        <v-col class="ma-5 pa-5 d-flex justify-center">
          <v-btn @click="clickedColor('red')" height=70px class="display-1 red white--text font-weight-bold">click me</v-btn>
    
        </v-col>

        <v-col class="ma-5 pa-5 d-flex justify-center">
          <v-btn @click="clickedColor('yellow')" height=70px class="display-1 yellow font-weight-bold">click me</v-btn>
        </v-col>

      </v-row>

      <div class="row ma-5 pa-5"></div>
      <div class="row ma-5 pa-5"></div>
      
      <!-- <hr class="blue lighten-4 mt-5"> -->
      
      <div class="mt-5 border border-blue">

        <v-row height="150px" v-show="green" :class="['green', {visible: visible}]">
          
          <v-btn text v-show="!closed" @click="closeIt"><v-icon class="white--text">close</v-icon></v-btn>
          
          
        </v-row>

        <v-row height="150px" v-show="red" :class="['red', {visible: visible}]">

          <v-btn text v-show="!closed" @click="closeIt"><v-icon class="white--text">close</v-icon></v-btn>

        </v-row>

        <v-row height="150px" v-show="yellow" :class="['yellow', {visible: visible}]">
          <v-btn text v-show="!closed" @click="closeIt"><v-icon>close</v-icon></v-btn>
        </v-row>

      </div>
      
    </v-container>

  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',

  data() {
    return {
      green: false,
      red: false,
      yellow: false,
      closed: false,
      visible: ""
    }
  },
  methods: {
    
    clickedColor(color) {
      if (color === "green") {
        this.green = true
        this.red = false
        this.yellow= false
        this.closed = false
      } else if (color === "red") {
        this.red = true
        this.green = false
        this.yellow= false
        this.closed = false
      } else if (color === "yellow") {
        this.green = false
        this.red = false
        this.yellow= true
        this.closed = false
      }
    },
    
    closeIt() {
      if (!this.closed) {
        this.closed = true
        this.visible = "d-none"
      } else {
        this.closed = false
        this.visible = ""
      }
    },
  },
}
</script>
