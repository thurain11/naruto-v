<template>
  <div class="team">
     <v-container >
        <v-layout row wrap>
          <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key='person.name'>
             <v-card flat class='text-xs-center ma-3'>
               <v-responsive class='pt-3'>
                
               </v-responsive>
                  <v-avatar
                    size="100"
                    class='grey lighten-2'
                  >
                    <img :src="person.avatar">
                  </v-avatar>

               <v-card-text>
                  <div class='subheading'>{{person.name}}</div>
                  <div class="grey--text">{{person.role}}</div>
               </v-card-text>
               <v-card-actions>
                  <v-btn small flat color="grey">message</v-btn>
               </v-card-actions>
             </v-card>
          </v-flex>
        </v-layout>

        

     </v-container>
   
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      team:[
        {name:'Thurain Hein',role:'Sonesinaphar',avatar: '/1.png'},
        {name:'Mg Tin Win',role: 'Web Developer',avatar: '/2.jpg'},
        {name:'Ma Khin Min',role: 'Web Designer',avatar:'/3.jpg'},
        {name:'U Hla Tun',role: 'project Manager',avatar:'/4.png'},
        {name:'Tun Mg',role: 'Sale guru',avatar:'/5.jpg'},
      ]
    }
  },
};
</script>
