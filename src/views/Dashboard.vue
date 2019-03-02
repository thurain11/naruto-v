<template>
  <div>
    <p class="subheading grey--text">Dashboard</p>
    <v-container>

      <v-layout row wrap class="mb-2">

         <v-tooltip top>
            <v-btn small flat class='grey--text' @click="sortBy('title')" slot="activator">
            <v-icon left>folder</v-icon>
         <span class="grey--text caption">Projects</span>
         </v-btn>
         <span>Sort by projects</span>
         </v-tooltip>


         <v-tooltip top >
            <v-btn small flat class='grey--text' @click="sortBy('person')" slot="activator">
            <v-icon left>person</v-icon>
         <span class="grey--text caption">Persons</span>
         </v-btn>
         <span>Sort by person</span>
         </v-tooltip>

         
      </v-layout>

      <v-card flat class="pa-3" v-for="project in projects" :key="project.due">
        <v-layout :class="`pa-2 project ${project.status}`" row wrap>
          <v-flex xs12 md6>
            <div class="caption grey--text">Project title</div>
            <div>{{project.title}}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{project.person}}</div>
          </v-flex>

          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>

          <v-flex xs2 sm4 md2>
            <div class='right'>
              <v-chip :class="`${project.status} caption white--text my-2` " small>{{project.status}}</v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default { 
  components: {},
  data() {
    return {
      projects: [
        {
          title: "Node Server",
          person: "Thurain Hein",
          due: "11 feb 2019",
          status: "ongoing",
          content: "Lorem ipsum dolor sit amet consectetur adipisicing elit."
        },
        {
          title: "ReactRouter",
          person: "Aye Thidar",
          due: "21 july 2017",
          status: "complete",
          content: "Lorem ipsum dolor sit amet consectetur adipisicing elit."
        },
        {
          title: "BabelTuto",
          person: "Mg Mg Thein",
          due: "14 dec 2018",
          status: "overdue",
          content: "Lorem ipsum dolor sit amet consectetur adipisicing elit."
        }
      ]
    };
  },

 methods: {
    sortBy(prop){
      this.projects.sort((a,b)=> a[prop]<b[prop]? -1: 1)
    }
  },
 
};
</script>


<style scoped>
   .project.complete{
     border-left: 4px solid rgba(25, 209, 230, 0.925);
   }
   .project.overdue{
     border-left: 4px solid rgba(217, 230, 47, 0.925);
   }
   .project.ongoing{
     border-left:4px solid rgba(42, 230, 25, 0.925);
   }


   .v-chip.complete{
     background: rgba(25, 209, 230, 0.925);
   }
   .v-chip.overdue{
     background: rgba(217, 230, 47, 0.925);
   }
   .v-chip.ongoing{
     background: rgba(42, 230, 25, 0.925);
   }
</style>
