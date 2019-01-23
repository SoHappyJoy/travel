<template>
    <div>
        <home-header></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :icons="iconList"></home-icons>
        <home-recommend :recommend="recommend"></home-recommend>
        <home-weekend :weekend="weekend"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper.vue'
import HomeIcons from './components/Icons.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
import {mapState} from 'vuex'
export default {
    name:'Home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcons,
        HomeRecommend,
        HomeWeekend
    },
    data (){
        return {
            lastCity:'',
            swiperList:[],
            iconList:[],
            recommend:[],
            weekend:[]
        }
    },
    computed:{
        //mapstate
        ...mapState(['city'])
    },
    methods: {
        getHomeInfo (){
             axios.get('./api/index.json?city='+this.city).then(
                this.getHomeInfoSucc
            )
        },
       getHomeInfoSucc(res){
           res=res.data;
           if(res.ret&&res.data){
               const data=res.data;
               this.swiperList=data.swiperList;
               this.iconList=data.iconList;
               this.recommend=data.recommendList;
               this.weekend=data.weekendList;
           }
       }
    },
    mounted (){
        this.lastCity=this.city;
        this.getHomeInfo()
    },
    activated (){
        if(this.lastCity!==this.city){
            this.lastCity=this.city;
            this.getHomeInfo()
        }
    }
}
</script>

<style>

</style>

