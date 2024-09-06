<template>
     
    <div class="headerNav">
    <div class="header-logo">
        <img src="../assets/img/newFotos.jpg" alt="">
    </div>
    <div class="header-search" >
          <div class="mt-4">
    <el-input
      v-model="input3"
      style="max-width: 600px"
      placeholder="Please input"
      class="input-with-select"
    >  
      <template #append>
        <el-button :icon="Search" />
      </template>
    </el-input>
  </div>
    </div>
    <div class="header-right">
    <el-link :icon="Edit">Login</el-link>
    <el-link target="_blank">Register</el-link>
     <el-dropdown>
    <span class="el-dropdown-link">
      meine Bestellung
      <el-icon class="el-icon--right">
        <arrow-down />
      </el-icon>
    </span>
    <template #dropdown>
      <el-dropdown-menu>
        <el-dropdown-item v-for="v in myBestellung" :key="v.id">{{ v.title }}</el-dropdown-item>
         
       
      </el-dropdown-menu>
    </template>
  </el-dropdown>
    </div>
    </div>

   
      
</template>
<script lang="ts" setup name="navMenu">
import { ref } from 'vue'
import { Search,Edit } from '@element-plus/icons-vue'
import { ArrowDown } from '@element-plus/icons-vue'

const input3 = ref('')
let myBestellung=[{id:1,title:"Busticket"},
    {id:2,title:"Hotel"},
    {id:3,title:"Flugticket"},
    {id:4,title:"Zugticket"},
    {id:5,title:"Restaurant"},
    {id:6,title:"Zoo"}
]


</script>
<style scoped>
.header-right .el-input-group__append{
    background-color: var(--el-color-primary);
    color: #fff;

}
.header-right .el-link{
    margin: 0 20px;
}
.example-showcase .el-dropdown-link {
  cursor: pointer;
  color: var(--el-color-primary);
  display: flex;
  align-items: center;
}

.headerNav{
    display: flex;
    justify-content: space-between;
    align-items:center ;
    position:fixed;
    top:0;
    background-color: #fff;
    z-index: 999;
   
   
}
.headerNav,div{
    margin-left: 20px;
}
.headerNav .el-button{
    background-color: var(--el-color-primary);

}
el-header{
    min-width: 1240px;
}
img{
    width: 200px;
    height: 60px;
}
.header-search{
    width: 600px;
}
.el-dropdown-link:focus{
    outline:none;
}

</style>

