<template>
  <v-app>
<load />
      
    <!--TOOLBAR-->
    <v-card tile color="transparent">
    <v-app-bar tile fixed  hide-on-scroll>
      <v-app-bar-nav-icon large color="black" @click.prevent="drawer = !drawer" class="hidden-md-and-up"></v-app-bar-nav-icon>
      <v-toolbar-title><img :src="require('./assets/logo.png')" class="logo"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-list  v-for="item in items" :key="item.title" color="transparent" flat class="hidden-sm-and-down">
        <v-btn color="transparent" depressed tile><a style="color:black" :href="item.link">{{item.title}}</a></v-btn>
      </v-list>
    </v-app-bar>
    </v-card>
    <!--NAVIGATION DRAWER-->
    <v-navigation-drawer v-model="drawer" temporary class="hidden-md-and-up" fixed>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title><img :src="require('./assets/logo.png')" class="logo-navigation"></v-list-item-title>
          <v-list-item-subtitle>Enjoy Life!</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon >
            <v-icon>{{item.icon}}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title><a style="color:black" :href="item.link">{{item.title}}</a></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

<router-view></router-view>
  </v-app>
</template>
<script>
import load from './components/Load'


export default {
  name: 'App',
  components: {
load,
  },
  data: () => ({
    items: [
      {title: 'Home', icon: 'home', link: '/'},
      {title: 'Reservation', icon: 'calendar_today', link: '#reservation'},
      {title: 'Facilities', icon: 'rowing', link: '#facilities'},
      {title: 'Accommodation', icon: 'panorama', link: '#accommodation'},
      {title: 'Location', icon: 'place', link: '#location'},
      {title: 'Contact', icon: 'local_post_office', link: '#contact'}
    ],
    drawer: false
  }),
  /*
      created: function() {
        window.onscroll = yHandler;
        //function
        function yHandler() {
            //get the first target
            const facilities = document.getElementById("facilities");
            const accommodation = document.getElementById("accommodation");
            //then get the height
            const facilitiesHeight = facilities.offsetHeight;
            const accommodationHeight = accommodation.offsetHeight;
            //get the windows height
            const wh = window.pageYOffset;

            //condition
            if (facilitiesHeight < wh) {
            //get the target in DOM
            document.getElementById("image-wrap").style.display = "flex"
            };
            if (accommodationHeight < wh) {
            //get the target in DOM
            document.getElementById("content-wrapper").style.display = "flex"
            }
        }
    } */

};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.logo {
  width: 130px;
  margin: 12px 0px 0px -20px;
}
.logo-navigation {
  width: 100px;
}
a {
  text-decoration: none;
  color: black
}

</style>
