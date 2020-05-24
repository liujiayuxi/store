<template>
    <div class="pic_item">
        <div class="item" v-for="(item,index) in storelist" :key="index">
            <div v-if="item.willdelete">
                <img class="pic" src="../assets/pic.png">
                <p class="name">{{item.name}}</p>
                <button @click="deleteItem(item)">删除</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "manager_delete",
        data(){
            return{
                storelist:[
                    {
                        name:'王者荣耀',
                        willdelete: true
                    },{
                        name:'和平精英',
                        willdelete: true
                    },{
                        name:'开心消消乐',
                        willdelete: true
                    },{
                        name:'网易云音乐',
                        willdelete: true
                    },{
                        name:'QQ音乐',
                        willdelete: true
                    },{
                        name:'微信',
                        willdelete: true
                    },{
                        name:'微博',
                        willdelete: true
                    },{
                        name:'QQ',
                        willdelete: true
                    },{
                        name:'盒马生鲜',
                        willdelete: true
                    },{
                        name:'抖音段视频',
                        willdelete: true
                    },{
                        name:'火山小视频',
                        willdelete: true
                    },{
                        name:'支付宝',
                        willdelete: true
                    }]
            }
        },
        methods:{
            deleteItem(item){
                setTimeout(() => {
                    alert(item.name + '删除成功');
                    item.willdelete = false;
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
