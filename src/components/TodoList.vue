<template>
  <ul>
    <li v-for="(item,i) in todoItem" :key="i" class="itemList">
      <div class="list">
        <i class="fa-regular fa-square-check"></i> 
        {{item}}
      </div>
      <div class="del" @click="removeDel(i,item)">
        <i class="fa-solid fa-eraser"></i>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
    props:[
        "todoItem"
    ],
    methods:{
      removeDel(num,item){
        this.$emit("reDel",num,item)
      }
    }
}
</script>

<style lang="scss">
  .itemList {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height:35px;
    // background: pink;
    margin-bottom: 10px;
    .list{
      display: flex;
      gap:10px
    }
    .del{
      background: skyblue;
      padding:0 20px;
      height: 100%;
      cursor:pointer;
      align-self:start;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
</style>