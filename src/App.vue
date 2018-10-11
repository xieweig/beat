<template>
  <div id="app">
    <el-container class="el-container" style="height: 500px; border: 1px solid #111">
      <el-header class="el-header" style="background-color: beige">欢迎进入武侠世界</el-header>
      <el-container class="el-container">
        <el-aside width="200px" class="el-aside">
        射雕英雄传
         <!-- <el-menu class="el-menu"
                   background-color="#553311"
                   text-color="#aaa"
                   active-text-color="#ffd04b">
            <el-submenu class="el-submenu" index="1">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>九阴真经</span>
              </template>
              <el-menu-item v-for="i in $router.options.routes"
                            :key="i.path" :index="i.name" >
                <i class="el-icon-document"></i>
                <span slot="title">
                <router-link :to=i.path>{{i.name}}</router-link>
                </span>
              </el-menu-item>
            </el-submenu>
            <el-submenu class="el-submenu" index="2">
              <template slot="title">
                <i class="el-icon-location-outline"></i>
                <span>华山论剑</span>
              </template>
              <el-menu-item>nice
              </el-menu-item>
            </el-submenu>
          </el-menu>-->
          <el-menu :default-active="$route.path" router="true">
            <el-submenu index="1">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>九阴真经</span>
              </template>
              <el-menu-item v-for="i in $router.options.routes"
                            :key="i.path" :index="i.path" v-if="!i.children">
                <i class="el-icon-document"></i>
                <span slot="title">{{i.name}}</span>
              </el-menu-item>
                <el-submenu v-for="i in $router.options.routes"
                              :key="i.path" :index="i.path" v-if="i.children">
                    <span slot="title">{{i.name}}</span>
                    <el-menu-item v-for="j in i.children"
                                :key="j.path" :index="j.path">
                        <i class="el-icon-document"></i>
                        <span slot="title">{{j.name}}</span>
                    </el-menu-item>
                </el-submenu>
            </el-submenu>

            <el-submenu index="2">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>华山论剑</span>
              </template>
              <el-menu-item index="/about">
                nice
              </el-menu-item>
            </el-submenu>
          </el-menu>

          <!--如下：配合if标签可以实现二级子菜单导航，关系类似于文件和目录，二级足够使用-->
          <!--    <el-menu :default-active="$route.path" class="el-menu-vertical-demo" router>
    //index设置的值为path
        <el-menu-item v-for="menu in menus" :index="menu.route" :key="menu.route" v-if="!menu.children">
            <i class="el-icon-menu"></i>{{menu.name}}
        </el-menu-item>
        <el-submenu v-for="menu in menus" :index="menu.route" :key="menu.route" v-if="menu.children">
            <template slot="title"><i class="el-icon-menu"></i>{{menu.name}}</template>
            <el-menu-item :index="item.route" v-for="item in menu.children" :key="item.route"> <i class="el-icon-location"></i>{{item.name}}</el-menu-item>
        </el-submenu>
    </el-menu>-->
        </el-aside>
        <el-main class="el-main"><router-view/></el-main>
      </el-container>
    </el-container>





  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
