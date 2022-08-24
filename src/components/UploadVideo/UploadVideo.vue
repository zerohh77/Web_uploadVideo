<template>
  <div>
    <el-container>
      <el-header class="header">
        <my-header></my-header>
      </el-header>
      <el-container>
        <el-aside width="150px" class="aside">
          <my-aside></my-aside>
        </el-aside>
        <el-main class="main">
          <my-main></my-main>
        </el-main>
      </el-container>

    </el-container>
  </div>
</template>

<script>
import MyMain from "@/components/UploadVideo/MyMain";
import MyHeader from "@/components/UploadVideo/MyHeader";
import MyAside from "@/components/UploadVideo/MyAside";

export default {
  name: "UploadVideo",
  components: {
    MyAside,
    MyMain,
    MyHeader
  }
}
</script>

<style scoped>
.header {
  background-color: #409EFF;
}

.main {
  background-color: #E9EEF3;
}

.aside{
  background-color: #D3DCE6;
}
</style>