<template>
    <div class="container" @click="handleGalleryClick">
        <div class="wrapper">
            <swiper :options="swiperOption">
                <!-- slides -->
                <swiper-slide v-for="(item,index) in imgs" :key="index">
                    <img class="gallery-img" :src="item" alt="">
                </swiper-slide>
                <div class="swiper-pagination"  slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
export default {
    name:'CommonGallery',
    props:{
        imgs:{
            type:Array,
            default(){
                return []
            }
        }
    },
    data (){
        return {
            swiperOption:{
                pagination:'.swiper-pagination',
                paginationType:'fraction',
                observeParents:true,
                observer:true
            }
        }
    },
    methods: {
        handleGalleryClick (){
            this.$emit('close')
        }
    }
}
</script>

<style lang="stylus" scoped>
.container >>> .swiper-pagination{
    bottom:-1rem;
}
.swiper-container{
    overflow:inherit;
}
.container{
    display:flex;
    flex-direction:column;
    justify-content :center;
    position:fixed;
    left:0;
    right:0;
    bottom:0;
    top:0;
    z-index :99;
    background:rgba(0,0,0,1);
    .wrapper{
        color:#fff;
        width:100%;
        height:0;
        padding-bottom:100%;
        .gallery-img{
            width:100%;
        }
    }
}
</style>
