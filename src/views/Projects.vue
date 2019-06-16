<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>

    <v-container class="my-5">
      <v-expansion-panel>
        <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
          <div slot="header">{{project.title}}</div>
          <v-card>
            <v-card-text class="px-4 grey--text">
              <div class="font-weight-bold">Due by: {{project.due}}</div>
              <div>{{project.content}}</div>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-container>
  </div>
</template>


<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Design a new website",
          person: "Amie",
          due: "October 21 2019",
          status: "ongoing"
        },
        {
          title: "Finish portfolio",
          person: "Luke",
          due: "December 21 2019",
          status: "need to begin"
        },
        {
          title: "Design thumbnails",
          person: "Evan",
          due: "November 15 2019",
          status: "Overdue"
        },
        {
          title: "create a forum",
          person: "Kayla",
          due: "August 21 2019",
          status: "Late"
        }
      ]
    };
  },
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === "Amie";
      });
    }
  }
};
</script>
