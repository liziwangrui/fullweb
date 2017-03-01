<template>
    <div class="main">
      <el-row>
        <el-col :span="24"><div class="grid-content bg-purple-dark"></div></el-col>
      </el-row>
        <div class="header">
          <div class="header-title">
            <p class="">导航</p>
            <i class="fa fa-bars" aria-hidden="true"></i>
          </div>
        </div>
        <div class="main-cnt">
          <div class="nav">
            <el-menu :router=true default-active="user" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose">
                  <el-menu-item v-for="item in menu" :index="item.router">
                      <i :class="item.icon"></i>{{item.name}}
                  </el-menu-item>
            </el-menu>
          </div>
          <div class="content">
              <router-view></router-view>
          </div>
        </div>
    </div>
</template>
<script>
    import menu from '../menu.js'
    export default {
        data() {
            return {
                menu: menu
            }
        },
        methods: {
            handleOpen(key, keyPath) {
                console.log(key, keyPath);
            },
            handleClose(key, keyPath) {
                console.log(key, keyPath);
            }
        }
    }
</script>
