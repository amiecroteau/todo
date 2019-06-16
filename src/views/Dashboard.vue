<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>
    <v-container class="my-5">
      <v-layout row class="mb-3">
        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
            <v-icon left small>folder</v-icon>
            <span class="caption text-lowercase">By Project Name</span>
          </v-btn>
          <span>Sort Project by Project Name</span>
        </v-tooltip>

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
            <v-icon left small>person</v-icon>
            <span class="caption text-lowercase">By Person</span>
          </v-btn>
          <span>Sort Project by Person Name</span>
        </v-tooltip>
      </v-layout>

      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project Title</div>
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
            <div class="right">
              <v-chip small :class="`${project.status} white--text caption my-2`">{{project.status}}</v-chip>
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

  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    }
  }
};
</script>

<style>
.project.ongoing {
  border-left: 4px solid green;
}
.project.need.to.begin {
  border-left: 4px solid navy;
}
.project.Late {
  border-left: 4px solid red;
}
.project.Overdue {
  border-left: 4px solid orange;
}

.v-chip.ongoing {
  background: green;
}
.v-chip.need.to.begin {
  background: navy;
}
.v-chip.Late {
  background: red;
}
.v-chip.Overdue {
  background: orange;
}
</style>

