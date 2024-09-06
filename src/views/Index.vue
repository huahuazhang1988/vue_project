

<template>
 <div class="common-layout">
    <el-container class="items">
      <el-aside width="200px"> <navMenu></navMenu></el-aside>
     
      <el-container>
      <el-header><headerNav></headerNav></el-header> 
      <el-main> <searchList></searchList> 
        <topFilter/>
        <recommend></recommend>
        <echarts></echarts>

      </el-main>
     
    </el-container>
      
     
  </el-container>
 
  </div> 
</template>
<script setup lang="ts" name="Index">
import echarts from './echarts.vue';
import recommend from './recommend.vue';
import topFilter from './topFilter.vue'
import navMenu  from './navMenu.vue';
import headerNav from './headerNav.vue';
import searchList from './searchList.vue';


</script>
<style scoped>
.items{
  display: flex;
}
element.style {
    max-width: 400px;
}

</style>
