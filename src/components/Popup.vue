<template>
  <v-dialog max-width="600px">
    <v-btn flat slot="activator" class="success">Add New Project</v-btn>
    <v-card>
      <v-card-title>
        <h2>Add a New Project</h2>
      </v-card-title>
        <v-card-text>
            <v-form class="px-3" ref="form">
               
                <v-text-field label="Title" v-model="title" prepend-icon="folder" :rules="inputRules"></v-text-field>
                <v-textarea label="Information" v-model="content" prepend-icon="edit" :rules="inputRules"></v-textarea>
                <v-menu>
                  <v-text-field :value="due" slot="activator" label="Due Date" prepend-icon="date_range" :rules="inputRules"></v-text-field>  
                <v-date-picker v-model="due"></v-date-picker>
                </v-menu>            

              <v-spacer></v-spacer>


                <v-btn clat class="success mx-0 mt-3" @click="submit"> Add Project </v-btn>            
            </v-form>
        </v-card-text>
    </v-card>
  </v-dialog>
</template>
<script>

export default {
    data(){
        return{
            title:'',
            content:'',
            due: null,
            inputRules:[
              v => v.length >= 3 || 'Minimum Length is 3 characters'
            ],
            loading: false
        }
    },
    methods:{
        submit(){
          if(this.$refs.form.validate()){
           
             console.log(this.title, this.content);
            

          }
           
        }
    },
    
    }


</script>

