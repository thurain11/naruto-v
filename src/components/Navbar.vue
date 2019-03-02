<template>
  <nav>
    <v-toolbar flat app>
      <v-toolbar-side-icon class="teal--text" @click="drawer = !drawer"></v-toolbar-side-icon>

      <v-toolbar-title class="teal--text text-uppercase font-weigth-bold">
        <span class="font-weight-light">Thurain</span>
        <span>Hein</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>


       <v-menu offset-y>
         <v-btn  color="grey" flat slot="activator">
           <v-icon left >expand_more</v-icon>
           <span>Menu</span>
         </v-btn>
         <v-list>
           <v-list-tile v-for="link in links" :key="link.text"  router :to='link.route'>
             <v-list-tile-title>{{ link.text }}</v-list-tile-title>
           </v-list-tile>
         </v-list>
       </v-menu>

      <v-btn flat color="grey">
        <span>Sign Out</span>
        <v-icon>exit_to_app</v-icon>
      </v-btn>
    </v-toolbar>

    <v-navigation-drawer v-model="drawer" app class="teal">

        <v-layout column  align-center>
           <v-flex class='mt-3'>
             <v-avatar
               size="100"
               color="grey"
             >
               <img src="/6.png" alt="alt">
             </v-avatar>
             <p class="subheading white--text mt-1 ">Thurain Hein</p>
           </v-flex>


           <v-flex>
              <Popup />
           </v-flex>
        </v-layout>


      <v-list>
        <v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
          <v-list-tile-action>
            <v-icon class="white--text">{{link.icon}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-title class="white--text">{{link.text}}</v-list-tile-title>
        </v-list-tile>
        
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>



<script>
import Popup from './Popup'
export default {
  components:{
       Popup
  },
  data() {
    return {
      drawer: false,
      links: [
        { icon: "dashboard", text: "Dashboard", route: "/" },
        { icon: "folder", text: "Projects", route: "/projects" },
        { icon: "person", text: "Team", route: "/team" }
      ]
    };
  },

};
</script>