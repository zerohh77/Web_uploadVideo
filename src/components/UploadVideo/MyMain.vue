<template>
  <div>
    <el-upload
        class="upload-demo"
        action="http://127.0.0.1:5000/upload"
        :on-preview="handlePreview"
        :on-remove="handleRemove"
        :on-success="handleSuccess"
        :before-remove="beforeRemove"
        multiple
        :limit="30"
        :on-exceed="handleExceed"
        :file-list="fileList">
      <el-button size="small" type="primary">点击上传</el-button>
      <div slot="tip" class="el-upload__tip">请上传格式正确的视频</div>
    </el-upload>
<!--    <video width="100%" height="590" :src="mydata" controls>-->
<!--    </video>-->
    <video id="video0" :src="mydata" controls="controls" type='video/mp4; codecs="avc1.4d002a"' style="margin: 5px;" width="80%"></video>
    <!--    <img :src="mydata">-->
  </div>
</template>

<script>
import eventBus from "@/EventBus";
export default {
  name: "MyMain",
  data() {
    return {
      fileList: [],
      data: '',
      mydata: ''
    };
  },
  methods: {
    handleRemove(file, fileList) {
      console.log(file, fileList);
    },
    handleSuccess(res) {
      this.mydata = 'http://127.0.0.1:5000/download'
      //this.mydata = 'data:video/mp4;base64,' + res.img
      //this.mydata = this.dataURLtoFile(this.data)
      // this.mydata = res
      console.log(res.img)
      eventBus.$emit("akita",[true,true,true,true,true])
    },
    handlePreview(file) {
      console.log(file);
    },
    handleExceed(files, fileList) {
      this.$message.warning(`当前限制选择 3 个文件，本次选择了 ${files.length} 个文件，共选择了 ${files.length + fileList.length} 个文件`);
    },
    beforeRemove(file, fileList) {
      return this.$confirm(`确定移除 ${file.name}？`);
    },
    dataURLtoFile(dataurl, filename) {
      let arr = dataurl.split(','), mime = arr[0].match(/:(.*?);/)[1]
      let bstr = atob(arr[1])
      console.log(bstr)
      return bstr
    }
  }
}
</script>

<style scoped>

</style>