<template>
    <div class="team">
        <h1 class="subheading gray--text">Team</h1>

        <v-container>
            <v-row>
                <v-col v-for="person in team" :key="person.name" cols="12" sm="4" md="3">
                    <v-card class="text-center ma-3">
                        <v-responsive class="pt-6 mb-10">
                            <v-avatar size="100">
                                <img :src="person.avatar">
                            </v-avatar>
                        </v-responsive>

                        <v-card-text>
                            <div>{{ person.name }}</div>
                            <div>{{ person.role }}</div>
                        </v-card-text>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
    export default{
        data(){
            return{
            team : [
                {name:"한송림",role:'Team leader',avatar:"images/photo1.png"},
                {name:"한송림",role:'Team leader',avatar:"images/photo2.png"},
                {name:"한송림",role:'Team leader',avatar:"images/photo3.png"},
                {name:"한송림",role:'Team leader',avatar:"images/photo4.png"},
                {name:"한송림",role:'Team leader',avatar:"images/photo5.png"}
            ]
            }
        }
    }
</script>