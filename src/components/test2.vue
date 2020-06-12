<!--  -->
<template>
<div>
    <button @click="add"> toggle </button>
      <transition-group name="list" tag="p" mode='out-in'>
    <span v-for="item in items" v-bind:key="item" class="list-item">
      {{ item }}
    </span>
  </transition-group>
    
</div>
</template>

<script>
export default {
data() {
return {
    toggle:true,
     items: [1,2,3,4,5,6,7,8,9],
     nextNum: 10
}
},
//生命周期 - 创建完成（访问当前this实例）
created() {

},
//生命周期 - 挂载完成（访问DOM元素）
mounted() {

},
methods:{
   
     add() {
      this.items.splice(0, 0, this.nextNum++)
       this.items.splice(this.items.length-1, 1)
    },
    remove: function () {
      this.items.splice(this.items.length-1, 1)
    },
}
}
</script>
<style scoped>
/* @import url(); 引入css类 */
.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-enter-active, .list-leave-active {
  transition: all 1s;
}
.list-enter, .list-leave-to
/* .list-leave-active for below version 2.1.8 */ {
  opacity: 0;
  transform: translateX(-30px);
}

</style>