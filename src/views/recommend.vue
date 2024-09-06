<template>
    <div class="recommend">
        <div class="left">
            <h2 style="margin-left: 40px; font-size:xx-large;">recommend hotels</h2>
            <recommend_list></recommend_list>


        </div>
        <div class="right">
            <banner></banner>
        </div>
    </div>
</template>
<script lang="ts" setup >
import banner from './banner.vue';
import recommend_list from './recommend_list.vue';
</script>
<style scoped>
.recommend{
    width: 1200px;
    display: flex;
    gap: 0 20px;
    padding: 10px 0;
    
}
.left{
    width:780px ;

}
.right{
    width: 400px;
  
    margin-top: 90px;
}
</style>