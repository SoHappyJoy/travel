<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" :src="item.imgUrl" alt="上海">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
    name:'HomeSwiper',
    data (){
        return {
            swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
            },
            swiperList:[{
                id:'0001',
                imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/3d1d67ef5d935c05fa838f57633141e2.jpg_750x200_cdadafd4.jpg'
            },{
                id:'0002',
                imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/52f2b38f2edd916076bf12d8343e77f2.jpg_750x200_0ca49857.jpg'
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active{
        background-color:#fff;
    }
.wrapper{
    overflow:hidden;
    width:100%;
    height:0;
    padding-bottom:26.67%;
    background-color:#eee;
    
    .swiper-img{
        width:100%;
    }
}
    
</style>

