<template>
  <v-container><!-- v-if="display"-->
    <v-span>Dealer ID : </v-span>
    <v-span><input placeholder="Enter Dealer ID" v-model="input.dealerId"/></v-span>
    <p>
    <span>Dealer Name : </span>
    <input placeholder="Enter Dealer Name" v-model="input.dealerName"/>
    <v-span><v-btn @click="SaveDealerName">Save</v-btn></v-span>
    </p>
    <v-span><h4> {{response}} </h4></v-span>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name : "AddDealer",
  props:{
  //  dealerName: String,
    display: Boolean
  },

  data (){
    return {
      input: {
        dealerId: "",
        dealerName: ""
      },
      response: ""
    };
  },

  computed:{
    displayThis:{
      get : function() {
        return this.display;
      },
      set : function(value) {
        this.display=value;
      }
    },
    dealerIds: {
      get : function() {
        return this.dealerId;
      },
      set : function(value) {
        this.dealerId = value;
      }
    },
    dealerNames: {
      get : function() {
        return this.dealerName;
      },
      set : function(value) {
        this.dealerName = value;
      }
    }
  },
  methods: {
    SaveDealerName() {
      window.console.log('Dealer Id :' + this.input.dealerId);
      window.console.log('Dealer Name :' + this.input.dealerName);

      axios({ method: "POST", "url": "https://httpbin.org/post", "data": this.input, "headers": { "content-type": "application/json" } }).then(result => {
        this.response = "Response = " + result.data;
      }, error => {
        this.console.error(error);
      });      
    }
  }
}
</script>