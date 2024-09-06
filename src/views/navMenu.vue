<template>
    <div>
    <el-aside width="200px" class="aside">
       
   <el-menu
    default-active="2"
    class="el-menu-vertical-demo"
    :collapse="isCollapse"
    @open="handleOpen"
    @close="handleClose"
  >
    <el-radio-group v-model="isCollapse" style="margin-bottom: 20px">
    <el-radio-button :value="false" v-show="isCollapse">expand</el-radio-button>
    <el-radio-button :value="true" v-show="!isCollapse">collapse</el-radio-button>
  </el-radio-group>
 <el-menu-item index="item.id" v-for="item in asideList" :key="item.id">
      <el-icon><component :is="item.icon" class="i"/></el-icon>
      <template #title>{{item.title}}</template>
    </el-menu-item>
    </el-menu>   
</el-aside> 
    </div>
</template>
<script lang="ts" setup name="navMenu">
import { ref } from 'vue'
import {
  Document,
  Menu as IconMenu,
  Location,
  Setting,Avatar,StarFilled,KnifeFork,Ticket
} from '@element-plus/icons-vue'
let asideList=[{id:1,title:"Busticket",icon:Document},
    {id:2,title:"Hotel",icon:Ticket},
    {id:3,title:"Flugticket",icon:Ticket},
    {id:4,title:"Zugticket",icon:Ticket},
    {id:5,title:"Restaurant",icon:KnifeFork},
    {id:6,title:"Zoo",icon:Location}
]

const isCollapse = ref(true)
const handleOpen = (key: string, keyPath: string[]) => {
  console.log(key, keyPath)
}
const handleClose = (key: string, keyPath: string[]) => {
  console.log(key, keyPath)
}
</script>
<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 300px;
  min-height: 400px;
}
l-menu-item{
    color: blue;
}
#title{
    color: blue;
}
.aside .el-menu {
    --el-menu-level: 0;
    height: 100vh;
}
.aside .i{
    font-size: 24px;
    font-weight: 500;
    margin-right: 5px;
}

</style>