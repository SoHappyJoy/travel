<template>
<div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
        <div class="iconfont header-abs-icon">&#xe624;</div>
    </router-link>
    <div class="header-fixd" 
        v-show="!showAbs"
        :style="opacityStyle"
    >
        <router-link to="/">
            <div class="iconfont header-fixed-back">&#xe624;</div>
        </router-link>
        景点详情
    </div>
</div>
</template>

<script>
export default {
    name:'DetailHeader',
    data (){
        return {
            showAbs:true,
            opacityStyle:{
                opacity:0
            }
        }
    },
    methods: {
        handleScroll(){
            const top=document.documentElement.scrollTop;
            if(top>60){
                let opacity=top/140;
                opacity=opacity>1 ? 1 : opacity;
                this.opacityStyle={opacity};
                this.showAbs=false;
            }else{
                this.showAbs=true;
            }
            
        }
    },
    activated (){
        window.addEventListener('scroll',this.handleScroll);
        
    },
    deactivated (){
        window.removeEventListener('scroll',this.handleScroll)
    }
} 
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl';
.header-abs{
    position:absolute;
    left:.2rem;
    top:.2rem;
    width:.8rem;
    height:.8rem;
    line-height:.8rem;
    text-align center;
    border-radius:50%;
    background:rgba(0,0,0,.8);
    .header-abs-icon{
        color:#fff;
    }
}
.header-fixd{
    position fixed;
    top:0;
    left:0;
    right:0;
    z-index:10;
    overflow:hidden;
    height:$headerHeight;
    line-height:$headerHeight;
    text-align center;
    color:#fff;
    background:$bgColor;
    font-size:.32rem;
    .header-fixed-back{
        width:.64rem;
        text-align:center;
        font-size:.32rem;
        position:absolute;
        top:0;
        left:0;
        color:#fff;
    }
}
</style>
