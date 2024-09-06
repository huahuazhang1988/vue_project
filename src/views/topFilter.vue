<template>
    <div class="topFilter">
        <div>
            <h4>location</h4>
        </div>
        <div>
     <el-tabs v-model="activeName" class="demo-tabs" @tab-click="handleClick">
    <el-tab-pane label="beliebte Orte" name="first">
        <el-button type="default">Nordsee</el-button>
         <el-button type="default">OstSee</el-button>
          <el-button type="default">Kreta</el-button>
           <el-button type="default">Teneriffa</el-button>
          

    </el-tab-pane>
    <el-tab-pane label="Hotel" name="second">
             <el-button type="default">Hotel Quinta do Lago
</el-button>
                  <el-button type="default">Dhawa Ihuru
</el-button>
                  <el-button type="default">allsun Hotel Eden Playa</el-button>
                    <el-button type="default">Rhodos</el-button>
    </el-tab-pane>

    <el-tab-pane label="Flughafen" name="third">
        <el-button type="default">Frankfurt</el-button>
        <el-button type="default">London</el-button>
        <el-button type="default">Hongkong</el-button>
         <el-button type="default">Tokio</el-button>
    </el-tab-pane>
    <el-tab-pane label="Landschaft" name="fourth">
          <el-button type="default">Meer</el-button>
        <el-button type="default">Bergen</el-button>
        <el-button type="default">Wald</el-button>
          <el-button type="default">See</el-button>
    </el-tab-pane>
  </el-tabs>
        </div>
        <div style="width: 100px;">
            <h4> Hotel preis</h4>
        </div>
        <div>
            <div class="topfilter-price" >
                <el-button type="info" size="small" v-for="(preis,i) in hotelPreis" :key="i">{{ preis }}</el-button>
            </div>
        </div>
        <div>
            <h4>filter</h4>
        </div>
        <div>
            <el-dropdown v-for="(v,i) in filterList" :key="i">
    <span class="el-dropdown-link">
     {{ v.title }}
      <el-icon class="el-icon--right">
        <arrow-down />
      </el-icon>
    </span>
    <template #dropdown>
      <el-dropdown-menu>
        <el-dropdown-item v-for="(k,i) in v.list" :key="i">{{ k }}</el-dropdown-item>
  
      </el-dropdown-menu>
    </template>
  </el-dropdown>
     

            
        </div>
        
        </div> 
</template>
<script lang="ts" setup>
import { ref } from 'vue'
import type { TabsPaneContext } from 'element-plus'
import { ArrowDown } from '@element-plus/icons-vue'
let hotelPreis=ref(['5 Sterne Hotel','4 Sterne Hotel','3 Sterne Hotel','2 Sterne Hotel','unten 300 $','unten 200 $'])
let filterList=ref([{title:'Früstück',list:['mit Frückstück','ohne Frückstück',' mehrere Frückstück']},
{title:'Payment',list:['online','onsite','paypal']},
{title:'ZimmerTyp',list:['verdoppelte Bett','Single Bett',' Großes Bett']}])

const activeName = ref('first');


const handleClick = (tab: TabsPaneContext, event: Event) => {
  
}
let topFilterlist=ref([
    {id:1,name:"first",label:"beliebte Orte",list:[]},
     {id:2,name:"second",label:"Hotel"},
      {id:3,name:"third",label:"Flughafen"},
       {id:4,name:"fourth",label:"Landschaft"},
])

</script>
<style scoped>
.example-showcase .el-dropdown-link {
  cursor: pointer;
  color: var(--el-color-primary);
  display: flex;
  align-items: center;
}
.topFilter el-button:hover{
    background-color: aquamarine;
}
.topfilter-price el-button{
 
  
}


.demo-tabs > .el-tabs__content {
  padding: 32px;
  color: #6b778c;
  font-size: 32px;
  font-weight: 600;
}
.topFilter{
    display: grid;
    width: 1200px;
    grid-template-columns: 100px 1fr;
    grid-template-rows:repeat(3,auto) ;
    margin-top: 1px;
}
.topFilter>div{
    border-bottom: 1px solid #ddd;
    padding: 1rem;
}
.topFilter h4{
    line-height: 40px;
    text-align: center;
}

</style>