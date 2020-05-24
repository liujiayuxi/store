<template>
    <div class="pic_item">
        <div class="item" v-for="(item,index) in storelist" :key="index">
            <img class="pic" src="../assets/pic.png">
            <p class="name">{{item.name}}</p>
            <button @click="load(item)" v-if="item.willload">下载</button>
            <button disabled="disabled" v-else>已下载</button>
        </div>
    </div>

</template>

<script>
    export default {
        name: "pic-item",
        data(){
            return{
                storelist:[
                    {
                        name:'王者荣耀',
                        willload: true
                    },{
                        name:'和平精英',
                        willload: true
                    },{
                        name:'开心消消乐',
                        willload: true
                    },{
                        name:'网易云音乐',
                        willload: true
                    },{
                        name:'QQ音乐',
                        willload: true
                    },{
                        name:'微信',
                        willload: true
                    },{
                        name:'微博',
                        willload: true
                    },{
                        name:'QQ',
                        willload: true
                    },{
                        name:'盒马生鲜',
                        willload: true
                    },{
                        name:'抖音段视频',
                        willload: true
                    },{
                        name:'火山小视频',
                        willload: true
                    },{
                        name:'支付宝',
                        willload: true
                    }]
            }
        },
        methods:{
            load(item){
                setTimeout(() => {
                    alert(item.name + '下载成功');
                    item.willload = false;
                },2000)
            }
        }
    }
</script>

<style scoped>
    .pic_item{
        /*width: 90vw;*/
        margin: 0 auto;
        /*background: palegoldenrod;*/
    }
    .item{
        display: inline-block;
        margin: 30px;
    }
    .pic{
        width: 60px;
        height: 48px;
    }
</style>
