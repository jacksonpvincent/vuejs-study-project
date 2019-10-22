<template>
  <v-container>
    <img src = "../assets/NissanCars.jpg"/>
    <!-- display the navigation bar -->
       <!-- navigation bar links -->
    <v-toolbar-items class='hidden-xs-only'>
      <v-btn flat v-for="item in items" :key="item.title" :to="item.link">
        <v-icon right>{{item.icon}}</v-icon>{{item.title}}
      </v-btn>
      <v-spacer></v-spacer>
    </v-toolbar-items>
    <p><v-input/></p>
  </v-container>
</template>
<script>

//import AddDealer from "AddDealer";

export default {
  computed: {
    items() {
      let menuItems =  [
        {
          title: 'Add Dealer',
          //icon: 'face',
          link: '/register'
        },
        {
          title: 'Update Dealer',
          //icon: 'face',
          link: '/register'
        },
        {
          title: 'Remove Dealer',
          //icon: 'face',
          link: '/register'
        },
        {
          title: 'Dealer Login',
          //icon: 'no_encryption',
          link: '/login'
        },
        {
          title: 'Dealer Search',
          //icon: 'no_encryption',
          link: '/login'
        }
      ]
    return menuItems
    }//,
    //components : {
    //  AddDealer
    //}
  },
  methods:{

  }
}
</script>