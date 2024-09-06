<template>
    <div class="recommend-list">
   <ul>
    <li v-for="item in recommendList" :key="item.id">
      <div class="list-left">
        <div class="list-left-img">  <img :src="item.imgUrl" alt=""></div>
         <div class="list-left-title">
            <div class="list-left-tagandtitle">
                <h4>{{ item.name }}</h4>
                 <img :src="item.starimg_url" alt="">
            </div>
            <div class="list-left-transport">
                <p>{{ item.transport }}</p>
            </div>
            <div class="list-left-tag" v-for="(v,i) in item.tag" :key="i">
                    <el-button type="info" size="small">{{v}}</el-button>
                         
   </div>
        </div>
        
        </div>     

       
      <div class="
       ">
        <div class="oben">
            <div class="comment">
                <div>good</div>
              <div>3333 Likes</div>
            </div>
            <div class="score" style="margin-left: 50px;">
                <p>4.5</p>
            </div>
          
              
        </div>
        <div class="unten">
            <div>$2999</div>
            <el-button type="primary" >checkdetail</el-button>
           
        </div></div>
    </li>
   </ul>
    </div>

</template>
<script lang="ts" setup>
import {ref} from 'vue';
let recommendList=ref([
    {id:1,name:"Zingst",imgUrl:'/src/assets/img/1.jpg',transport:'von StadtZentrum 200 meter',starimg_url:'/src/assets/img/13.jpg',tag:['Football','Swimmingpool','Fitnessstudio','Mensa','Sauna']},
      {id:2,name:"Cuxhaven",imgUrl:'/src/assets/img/2.jpg',transport:' mit bus 10 min zu Strand',starimg_url:'/src/assets/img/13.jpg',tag:['Football','Swimmingpool','Fitnessstudio','Mensa','Sauna']},
        {id:3,name:"Warnmünde",imgUrl:'/src/assets/img/3.jpg',transport:'von StadtZentrum 2 km',starimg_url:'/src/assets/img/13.jpg',tag:['Football','Swimmingpool','Fitnessstudio','Mensa','Sauna']},
          {id:4,name:"Rügen",imgUrl:'/src/assets/img/4.jpg',transport:'in der Näh von Flughafen',starimg_url:'/src/assets/img/13.jpg',tag:['Football','Swimmingpool','Fitnessstudio','Mensa','Sauna']},
            {id:5,name:"Usedom",imgUrl:'/src/assets/img/5.jpg',transport:'Schiff',starimg_url:'/src/assets/img/13.jpg',tag:['Football','Swimmingpool','Fitnessstudio','Mensa','Sauna']}

])
</script>
<style scoped>
.score p{
    color: var(--el-color-primary);
    font-size: 20px;
    font-weight: 700;
    background: skyblue;
}
.oben{
    display: flex;
    color: blue;
    margin-bottom: 50px;
    justify-content: flex-end;
    font-weight: 900;
    
}
.unten{
     color: blue;
    

}
.list-left-tag el-button{
    display: grid;
}

.recommend-list ul li{
    display: flex;
    background-color: silver;
    padding: 10px;
    margin-bottom: 10px;
}
.list-left{
    flex:2;
    display: flex;
}
.list-right{
    flex:1;
    border-left: 1px solid black;
    text-align: center;
}
 img{
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.list-left-img{
    flex:2
}
.list-left-title{
    flex: 3;
    margin-left:10px;
    color: black;
}
.list-left-tagandtitle{
    font-size: 18px;
    line-height: 24px;
    display: flex;
    margin-bottom: 8px;
    align-items: center;
    
}
.list-left-tagandtitle img{
    height: 24px;
    width: 100px;
   
    margin: 0 10px;
    
}
</style>