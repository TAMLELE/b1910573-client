<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item>
      <v-list-item-content>
      <v-list-item-title>
        NỘI DUNG
      </v-list-item-title>
      </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list dense>
        <v-list-item-group color="primary" >
          <v-list-item v-for="(item, i) in items" :key="i" :to="item.link" link >
            <v-list-item-icon>
              <v-icon v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title> GIỚI THIỆU ĐỊA ĐIỂM CHECK-IN VÀ ĐẶC SẢN CỦA HẬU GIANG</v-toolbar-title>
     
    </v-app-bar>
    

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>



<script>
  export default {
    data: () => ({
      drawer: null,
      items: [
        { title: 'Trang chủ', icon: 'mdi-home', link: "/" },
        { title: 'Thêm mới', icon: 'mdi-note', link: "/add-post" },
        { title: 'Giới thiệu', icon: 'mdi-help-box', link: "/about" },
      ],
    }),
  }
</script>