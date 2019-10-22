<template>
  <v-app>
    <nav-bar></nav-bar>
    <add-dealer></add-dealer>
 </v-app>
</template>

<script>
//import HelloWorld from "./components/HelloWorld";
import NavBar from "./components/NavBar";
import AddDealer from "./components/AddDealer";

export default {
  name: "App",
  components: {
    //HelloWorld,
    NavBar,
    AddDealer
  },
  data: () => ({
    //
  })
};
</script>
