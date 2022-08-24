<template>
  <div style="margin-top: 150px">
    <el-checkbox v-model:checked="my_check[0]"  label="烟雾报警" border class="el-checkbox-width"></el-checkbox>
    <el-checkbox v-model:checked="my_check[1]"  label="滴漏报警" border class="el-checkbox-width"></el-checkbox>
    <el-checkbox v-model:checked="my_check[2]"  label="火焰报警" border class="el-checkbox-width"></el-checkbox>
    <el-checkbox v-model:checked="my_check[3]"  label="煤粉报警" border class="el-checkbox-width"></el-checkbox>
    <el-checkbox v-model:checked="my_check[4]"  label="人员报警" border class="el-checkbox-width"></el-checkbox>
  </div>
</template>

<script>
import eventBus from "@/EventBus";
export default {
  name: "MyAside",
  data() {
    return {
      checkList: ['选中且禁用', '复选框 A'],
      my_check: [false,false,false,false,false]
    };
  },
  mounted() {
    eventBus.$on("akita",(my)=>{
      this.my_check=my
    })
  }
}
</script>

<style scoped>
.el-checkbox-width{
  margin-left: 0px;
  margin-right: 25px;
  width: 240px;
  padding-left: 0px;
  text-align: left;
}
</style>