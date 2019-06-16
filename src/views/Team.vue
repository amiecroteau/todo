<template>

<div class="team">
    <h1 class="subheading grey--text">Team</h1>
    <v-container class="my-5">
    <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
            <v-card flat class="text-xs-center ma-3">
                <v-responsive class="pt-4">
                    <v-avatar size="100">
                        <img :src="person.avatar" alt="">
                    </v-avatar>
                </v-responsive>
                <v-card-text>
                    <div class="subheading">{{person.name}}</div>
                    <div class="grey--text">{{person.role}}</div>
                </v-card-text>
                <v-btn flat color="grey">
                   <v-icon small left>message</v-icon>
                   <span>Message</span>
                </v-btn>
                <v-card-actions></v-card-actions>
            </v-card>

        </v-flex>
    </v-layout>
    </v-container>



</div>





</template>

<script>
export default {
    data(){
        return{
            team:[
                {name:'Amie Croteau', role:'Project Manager and Front-End Developer', avatar:'/avatar-1.png'},
                {name:'Bryan Cruz', role:'Front-End Architect and Developer', avatar:'/avatar-2.png'},
                {name:'Ethan Adams', role:'Artifical Intelligence Specialist and Developer', avatar:'/avatar-3.png'},
                {name:'Ian Morrissey', role:'Data Management Architect and Solution Specialist', avatar:'/avatar-4.png'},
                {name:'Austin Tucker', role:'User Experiance Specialist and Data Analyst', avatar:'/avatar-5.png'}
            ]
        }
    }
}
</script>
