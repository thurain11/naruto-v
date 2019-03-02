<template>
    
        <v-dialog max-width="500px">
            <v-btn slot="activator" small class="grey white--text small">Add New Project</v-btn>
            <v-card>
                <v-card-title >
                    <h2>Add New Project</h2>
                </v-card-title>
                <v-card-text>
                    <v-text-field color="teal" box label="Title" v-model="title" prepend-icon="folder"></v-text-field>
                    <v-text-field color="teal" box label="Content" v-model="content" prepend-icon="edit"></v-text-field>
                    <v-menu offset-y>
                        <v-text-field
                            label="Due date"
                            slot="activator"
                            prepend-icon="date_range"
                            :value="formatDate"
                        ></v-text-field>
                        <v-date-picker v-model="due" ></v-date-picker>
                    </v-menu>
                    <v-btn  color="teal white--text" @click="submit">Add new project</v-btn>
                </v-card-text>
            </v-card>
        </v-dialog>
    
</template>


<script>
import format from 'date-fns/format'
export default {
    data() {
        return {
            title:'',
            content:'',
            due: null,
        }
    },
    methods: {
        submit(){
            console.log(this.title, this.content);
            
        }
    },
    computed: {
        formatDate(){
            return this.due ? format(this.due,'Do MMM YYYY') : ''
        }
    },
}
</script>