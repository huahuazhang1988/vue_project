<template>
     <div class="block text-center" m="t-4">
    <span class="demonstration"></span>
    <el-carousel trigger="click" height="1200px" >
      <el-carousel-item v-for="item in imgList" :key="item">
        <img :src="item" alt="">
         
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script lang="ts" setup name="banner">
import {ref} from 'vue';
let imgList=ref(["/src/assets/img/1.jpg","/src/assets/img/2.jpg",
"/src/assets/img/3.jpg","/src/assets/img/4.jpg","/src/assets/img/5.jpg" 

])
</script>
<style scoped>
.block {
  
}
.demonstration {
  color: var(--el-text-color-secondary);
}

.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
img{
    width: 100%;
    height: 100%;
    object-fit: cover;

}
</style>