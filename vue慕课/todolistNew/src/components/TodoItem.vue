<template>
    <li class="item" @click="handleDelete">{{content}}</li>
</template>
<script>
export default {
    props:["content","index"],
    methods:{
        handleDelete(){
            console.log(this);
            this.$emit('delete',this.index);
        }
    }
}
</script>
<style scoped>
    /* scoped  样式可以向下渲染，不可以向上渲染 */
    .item{
        color:blueviolet
    }
</style>
