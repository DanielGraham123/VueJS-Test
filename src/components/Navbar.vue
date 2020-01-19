<template>
    <nav>
        <v-toolbar fixed app class="primary" >
            <v-app-bar-nav-icon class="white--text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
            
            <v-toolbar-title app class="text-uppercase font-weight-medium white--text">
                <span class="font-weight-light">Todo</span>
                <span>Ninja</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>

            <v-btn icon color="white">
                <v-icon>mdi-magnify</v-icon>
            </v-btn>

            <v-btn flat text color="white">
                <span>Sign Out</span>
                <v-icon right>exit_to_app</v-icon>
            </v-btn>
        </v-toolbar>

         <v-navigation-drawer fixed app temporary v-model="drawer" width="325" class="deep-purple lighten-5">
            
           <v-list-item two-line class="primary pa-5 ">
                <v-list-item-avatar>
                    <img src="@/assets/code.jpg">
                </v-list-item-avatar>

                <v-list-item-content>
                    <v-list-item-title class="headline white--text">
                        <span class="font-weight-light">Todo</span>
                        <span>Ninja</span>
                    </v-list-item-title>
                    <v-list-item-subtitle class="subtitle-1 white--text">
                        Subtext
                    </v-list-item-subtitle>
                </v-list-item-content>
            </v-list-item>

            <v-divider></v-divider>

            <v-list nav dense class="pa-0">
                <v-list-item v-for="link in links" :key="link.text" link router :to="link.route" class="py-3">
                    <v-list-item-icon>
                        <v-icon>{{ link.icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title class="body-1">{{ link.text }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>

        </v-navigation-drawer>
    </nav>
        
</template>

<script>
export default {

    data() {
        return {
            drawer: false, 
            links: [
                { icon: 'dashboard', text: 'Dashboard', route: '/' },
                { icon: 'folder', text: 'My Projects', route: '/projects' },
                { icon: 'person', text: 'Team', route: '/team' },
            ],
        }
    }
    
}
</script>