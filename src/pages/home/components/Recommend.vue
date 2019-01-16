<template>
    <div>
        <div class="recommend-title">
            热销推荐
        </div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
                
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:'',
    data (){
        return {
            recommendList:[{
                id:'0001',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0002',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0003',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0004',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0005',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0006',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0007',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            },{
                id:'0008',
                imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
                title:'上海迪士尼乐园',
                desc:'快乐童年记忆，亲子乐园'
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/ellipsis.styl'
.recommend-title{
    line-height:.8rem;
    background:#eee;
    text-indent:.2rem;
    margin-top:.2rem;
}
.item{
    display:flex;
    overflow:hidden;
    height:1.9rem;
    .item-img{
        width:1.7rem;
        height:1.7rem;
        padding:.1rem;
    }
}
.item-info{
    flex:1;
    padding:.1rem;
    min-width:0;
    .item-title{
        line-height:.54rem;
        font-size:.32rem;
        ellipsis()
    }
    .item-desc{
        line-height:.4rem;
        color:#ccc;
        ellipsis()
    }
    .item-button{
        line-height:.44rem;
        margin-top:.16rem;
        background:#ff9300;
        padding:0 .2rem;
        border-radius:.06rem;
        color:#fff;
    }
}
</style>
