<template>
    <v-navigation-drawer app color="black" right width="290">
        
        <v-toolbar color="rgba(0,0,0,0)" flat>
            <v-toolbar-title>Epics</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn rounded small>
                See All
            </v-btn>
        </v-toolbar>
        
        <v-list subheader two-line class="mt-n4">
            <v-list-item v-for="file in files" :key="file.title">
                <v-list-item-avatar>
                    <v-icon :class="file.color" dark v-text="file.icon" small></v-icon>
                </v-list-item-avatar>
                <v-list-item-content>
                    <v-list-item-title v-text="file.title"></v-list-item-title>
                    <v-list-item-subtitle v-text="file.subtitle"></v-list-item-subtitle>
                </v-list-item-content>
                <v-list-item-action>
                    <v-btn icon>
                        <v-icon color="white" small>fas fa-ellipsis-h</v-icon>
                    </v-btn>
                </v-list-item-action>
            </v-list-item>
        </v-list>
        
        <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n6">
            <v-toolbar-title>Call Statistics</v-toolbar-title>
        </v-toolbar>
        
        <v-card class="mx-2 rounded-1-xl pb-1 mt-5" flat color="#EEEEEEE">
            <v-row>
                <v-col cols="12" sm="5">
                    <v-list-item two-line class="mt-n4">
                        <v-list-item-content>
                            <v-list-item-title>
                                To do
                            </v-list-item-title>
                            <v-list-item-subtitle class="">
                                Progress
                            </v-list-item-subtitle>
                        </v-list-item-content>
                    </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-progress-circular 
                        :size="50" 
                        :width="3" 
                        :value="75"
                        color="yellow"
                        class="ml-n5 mt-n1">
                        75
                    </v-progress-circular>
                </v-col>
                <v-col cols="12" sm="3" class="mt-2">
                    <span class="ml-n8">Percent</span>
                </v-col>
            </v-row>
        </v-card>

        <v-card class="mx-2 rounded-1-xl pb-1 mt-5" flat color="#EEEEEEE">
            <v-row>
                <v-col cols="12" sm="5">
                    <v-list-item two-line class="mt-n4">
                        <v-list-item-content>
                            <v-list-item-title>
                                Happy
                            </v-list-item-title>
                            <v-list-item-subtitle class="">
                                Progress
                            </v-list-item-subtitle>
                        </v-list-item-content>
                    </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-progress-circular 
                        :size="50" 
                        :width="3" 
                        :value="45"
                        color="teal"
                        class="ml-n5 mt-n1">
                        45
                    </v-progress-circular>
                </v-col>
                <v-col cols="12" sm="3" class="mt-2">
                    <span class="ml-n8">Percent</span>
                </v-col>
            </v-row>
        </v-card>

        <v-card class="mx-2 rounded-1-xl pb-1 mt-5" flat color="#EEEEEEE">
            <v-row>
                <v-col cols="12" sm="5">
                    <v-list-item two-line class="mt-n4">
                        <v-list-item-content>
                            <v-list-item-title>
                                Done
                            </v-list-item-title>
                            <v-list-item-subtitle class="">
                                Progress
                            </v-list-item-subtitle>
                        </v-list-item-content>
                    </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-progress-circular 
                        :size="50" 
                        :width="3" 
                        :value="20"
                        color="red"
                        class="ml-n5 mt-n1">
                        20
                    </v-progress-circular>
                </v-col>
                <v-col cols="12" sm="3" class="mt-2">
                    <span class="ml-n8">Percent</span>
                </v-col>
            </v-row>
        </v-card>
        <div class="mt-2 mx-2">
            <v-btn rounded small block>
                Call History details
            </v-btn>
        </div>
    </v-navigation-drawer>
</template>

<script>
export default {
data: () => ({
    files: [
        {
            color: 'green',
            icon: 'fas fa-mobile',
            subtitle: 'Design',
            title: 'Mobile Onboarding'
        },
        {
            color: 'red',
            icon: 'fas fa-address-card',
            subtitle: 'Development',
            title: 'Adding Item '
        },
        {
            color: 'blue',
            icon: 'fas fa-user-shield',
            subtitle: 'Design',
            title: 'Mobile Onboarding'
        },
        {
            color: 'purple',
            icon: 'fas fa-file-code',
            subtitle: 'Design',
            title: 'Mobile Onboarding'
        },
        {
            color: 'yellow',
            icon: 'fas fa-drafting-compass',
            subtitle: 'Design',
            title: 'Mobile Onboarding'
        }
    ]
})
}
</script>

<style>

</style>