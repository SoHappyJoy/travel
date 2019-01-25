<template>
<div>
    <div class="banner" @click="handleBannerClick">
        <img class="banner-img" :src="bannerImg" alt="">
        <div class="banner-info">
            <div class="banner-title">{{this.sightName}}</div>
            <div class="banner-number">
                <span class="iconfont banner-icon">&#xe616;</span>
                {{this.bannerImgs.length}}
            </div>
        </div>
    </div>
    <common-gallery 
        :imgs="bannerImgs" 
        v-show="showGallery" 
        @close="handleGalleryClose"
    ></common-gallery>
</div>
</template>

<script>
import CommonGallery from '../../../common/gallery/Gallery'
export default {
    name:'DetailBanner',
    props:{
        sightName:String,
        bannerImg:String,
        bannerImgs:Array
    },
    data(){
        return {
            showGallery:false,
            imgs:['http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg','http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_r_800x800_6edd8174.jpg']
        }
    },
    methods:{
        handleBannerClick(){
            this.showGallery=true
        },
        handleGalleryClose(){
            this.showGallery=false
        }
    },
    components:{
        CommonGallery
    }
}
</script>

<style lang="stylus" scoped>
.banner{
    overflow:hidden;
    position:relative;
    height:0;
    padding-bottom:55%;
    .banner-img{
        width:100%;
    }
    .banner-info{
        display:flex;
        position:absolute;
        left:0;
        right:0;
        bottom:0;
        line-height:.6rem;
        color:#fff;
        background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8));
        .banner-title{
            flex:1;
            font-size:.32rem;
            padding:0 .2rem;
        }
        .banner-number{
            padding:0 .4rem;
            margin-top:.14rem;
            height:.32rem;
            line-height:.32rem;
            font-size:.24rem;
            border-radius:.2rem;
            background:rgba(0,0,0,.8);
            .banner-icon{
                font-size:.24rem;
                margin-right:.1rem;
            }
        }
    }
}
</style>
