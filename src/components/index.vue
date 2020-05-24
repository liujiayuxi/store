<template>
    <div class="index">
        <div class="manage">
            <button class="manage-btn">管理</button>
        </div>

        <PicItem></PicItem>
    </div>
</template>

<script>
    import PicItem from './pic-item.vue'
    export default {
        name: "index",
        components: {
            PicItem
        }
    }
</script>

<style scoped>
    .index{
        padding: 20px 0;
    }
    .manage{
        width: 60px;
        height: 30px;
        margin: 20px;
        margin-left: 92%;
    }
    .manage-btn{
        width: 60px;
        height: 30px;

    }
</style>
