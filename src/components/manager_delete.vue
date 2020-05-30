<template>
    <div class="pic_item">
        <div class="item" v-for="(item,index) in storelist" :key="index">

                <img class="pic" :src='item.iconUrl'>
                <div class="word">
                    <p class="line">
                        <span class="name">{{item.name}}</span>
                    </p>
                    <p class="line">
                        <span class="version">版本 {{item.version}}</span>
                        <span class="size">大小 {{item.size}}</span>
                    </p>
                    <p class="line">
                        <span class="time">更新时间 {{item.time}}</span>
                    </p>
                    <p class="line">
                        <button @click="deleteItem(item.id)">删除</button>
                    </p>
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
                // {
                //     id: 1,
                //     name:'王者荣耀',
                //     version:'0.0.1',
                //     size:'2.0G',
                //     time:'2020-05-26',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 2,
                //     name:'和平精英',
                //     version:'4.0.1',
                //     size:'1.78G',
                //     time:'2020-04-23',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 3,
                //     name:'开心消消乐',
                //     version:'0.2.1',
                //     size:'50.8M',
                //     time:'2020-03-20',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 4,
                //     name:'网易云音乐',
                //     version:'2.0.1',
                //     size:'248.0M',
                //     time:'2020-04-10',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 5,
                //     name:'QQ音乐',
                //     version:'0.3.1',
                //     size:'498.0M',
                //     time:'2020-03-28',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 6,
                //     name:'微信',
                //     version:'3.0.1',
                //     size:'1.2G',
                //     time:'2020-04-15',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 7,
                //     name:'微博',
                //     version:'0.0.2',
                //     size:'939M',
                //     time:'2020-04-30',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 8,
                //     name:'QQ',
                //     version:'0.2.1',
                //     size:'1.35G',
                //     time:'2020-05-08',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 9,
                //     name:'盒马生鲜',
                //     version:'2.0.1',
                //     size:'518.0M',
                //     time:'2020-05-04',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 10,
                //     name:'抖音段视频',
                //     version:'1.0.1',
                //     size:'128.0M',
                //     time:'2020-05-17',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 11,
                //     name:'火山小视频',
                //     version:'0.1.1',
                //     size:'98.0M',
                //     time:'2020-04-12',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // },{
                //     id: 12,
                //     name:'支付宝',
                //     version:'1.0.0',
                //     size:'635.0M',
                //     time:'2020-05-24',
                //     iconUrl:"xxxxx",
                //     downloadUrl:"xxxxx"
                // }
                ]
            }
        },
        mounted(){
            this.getData();
        },
        methods:{
            deleteItem(id){
                // setTimeout(() => {
                //     alert(item.name + '删除成功');
                //     this.storelist = this.storelist.filter(i => {
                //         return i.name != item.name;
                //     });
                // },2000)
                this.$axios({
                    method: 'post',
                    url: '/deleteApp',
                    contentType: 'application/x-www-form-urlencoded',
                    data: {id},
                }).then(res => {
                    let message = res.data.msg;
                    alert(message);
                    this.getData();
                }).catch(e => {
                    console.log(e);
                })
            },
            getData(){
                this.$axios.get('/getList').then(res => {
                    let data = res.data;
                    data.forEach(item => {
                        this.storelist.push(item);
                    })
                }).catch(e => {
                    console.log(e);
                })
            }
        }
    }
</script>

<style scoped>
    @import '../assets/css/style.css';

</style>
