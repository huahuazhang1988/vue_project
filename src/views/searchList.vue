<template>
    
   <div class="searchlist">
    <div class="searchItem">
     <div class="search-box">
       <label for="hotel-destination">Hotel Destinanion</label>
      <input type="text" id="hotel-destination" placeholder="please input your destination">
     </div>
    </div>
    <div class="searchItem">
      <div class="search-box">
       <label for="room-person">Rooms und Person</label>
      <input type="text" id="room-person" placeholder="please input rooms and persons">
     </div>
    </div>
    <div class="searchItem">
       <div class="search-box">
       <label for="keyword">Keyword</label>
      <input type="text" id="keyword" placeholder="please input keyword">
     </div>
    </div>
    <div class="searchItem">
       <div class="search-box">
       <label >From when to when</label>
       <div class="demo-date-picker">
    <div class="block">
      
      <el-date-picker
        v-model="value1"
        type="daterange"
        range-separator="To"
        start-placeholder="Start date"
        end-placeholder="End date"
        :size="size"/>
    </div>
      </div>
    </div>
  </div>
  <!--search-->
     <div class="searchItem">
      <div class="search-box">
        <el-button type="primary" :icon="Search">Search</el-button>
      </div>
    </div>
   </div>
</template>
<script lang="ts" setup>
import { reactive } from 'vue'
import { ref } from 'vue'
import { Delete, Edit, Search, Share, Upload } from '@element-plus/icons-vue'
const value1 = ref('');
const shortcuts = [
  {
    text: 'Last week',
    value: () => {
      const end = new Date()
      const start = new Date()
      start.setTime(start.getTime() - 3600 * 1000 * 24 * 7)
      return [start, end]
    },
  },
  {
    text: 'Last month',
    value: () => {
      const end = new Date()
      const start = new Date()
      start.setTime(start.getTime() - 3600 * 1000 * 24 * 30)
      return [start, end]
    },
  },
  {
    text: 'Last 3 months',
    value: () => {
      const end = new Date()
      const start = new Date()
      start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
      return [start, end]
    },
  },
  {
    text: 'Last 3 months',
    value: () => {
      const end = new Date()
      const start = new Date()
      start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
      return [start, end]
    },
  }
]
</script>


<style scoped>
.searchItem el-button{
  height: 100%;
  width: 100%;
  border-radius: 0;
}
.demo-date-picker {
  display: flex;
  width: 100%;
  padding: 0;
  flex-wrap: wrap;
}

.demo-date-picker .block {
  padding: 30px 0;
  text-align: center;
  border-right: solid 1px var(--el-border-color);
  flex: 1;
}

.demo-date-picker .block:last-child {
  border-right: none;
}

.demo-date-picker .demonstration {
  display: block;
  color: var(--el-text-color-secondary);
  font-size: 14px;
  margin-bottom: 20px;
}
.search-box{
  padding:8px 12px;
}
.search-box label{
  color: #999;
  display: block;
}
.search-box input{
  border:0;
  font-size: 16px;
  padding-top: 10px;
}
.searchlist{

  width: 1200px;
  display: grid;
  grid-template-columns: repeat(5,auto);
}
.searchItem{
  border:1px solid #dadada;
  margin-left: -1px;
}
.searchItem :focus-within{
  border-bottom: 1px solid var(--el-color-primary);
}
</style>