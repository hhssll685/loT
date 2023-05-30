<template>
  <div>
    <h1 class="subheading gray-text">Dashboard</h1>
    <v-main>
      <v-container>
        <!---->
        <v-row class="mb-3 ml-2">
          <v-btn small plain @click="$event => sortBy('title')">
            <span>by project title</span>
          </v-btn>
          <v-btn small plain @click="$event => sortBy('person')">
            <span>by person </span>
          </v-btn>


        </v-row>
        <!---->
        <v-card v-for="project in projects" :key="project.title" flat class="gray lighten-4">
          <v-row no-gutters wrap :class="`pa-3 project ${project.state}`">
            <!--title-->
            <v-col cols="12" md="6">
              <div class="caption gray--text">Project Title</div>
              <div>{{ project.title }}</div>
            </v-col>
            <!--person-->
            <v-col cols="4" sm="4" md="2">
              <div class="caption gray--text">Person</div>
              <div>{{ project.person }}</div>
            </v-col>
            <!--Due-->
            <v-col cols="8" sm="5" md="2">
              <div class="caption gray--text">Due</div>
              <div>{{ project.due }}</div>
            </v-col>
            <!--state-->
            <v-col cols="4" sm="3" md="2" class="pl-4">
              <div class="caption gray--text">State</div>
              <div :class="`${project.state} state`">{{ project.state }}</div>
            </v-col>
          </v-row>
        </v-card>
      </v-container>
    </v-main>
  </div>
  
</template>

<script>
  export default {
    data(){
      return{
        projects : [
          {title:'데이터베이스 저장 항목',person:'한송림',due:'2019.01.06',state:'completed'},
          {title:'안드로이드폰 시뮬레이터 개발',person:'한송림',due:'2020.03.25',state:'completed'},
          {title:'컴퓨터 비전',person:'한송림',due:'2021.05.15',state:'ongoing'},
          {title:'사진 변경 항목',person:'한송림',due:'2022.07.19',state:'completed'},
          {title:'안드로이드폰 개발 계산기',person:'한송림',due:'2023.03.12',state:'ongoing'}
        ]
      }
    },
    methods : {
      sortBy(prop){
        this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
      }
    }
  
  }
</script>



<style>
  .project.completed{
    border-left: 4px solid skyblue;
  }
  .project.ongoing{
    border-left: 4px solid orange;
  }

  .state.completed{
    color: skyblue;
  }
  .state.ongoing{
    color: orange;
  }
</style>