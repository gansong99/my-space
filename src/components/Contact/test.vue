<template>
  <div class="test-container">
    <Contact
      v-for="n in data"
      :key="n.id"
      :type="n.type"
      :typeName="n.typeId"
      :srcImg="n.srcImg"
    />
  </div>
</template>

<script>
import Contact from "@/components/Contact"
export default {
  components: {
    Contact
  },
  data () {
    return {
      data: [
        { id: 1, type: "github", typeId: "gansong99", srcImg: "" },
        { id: 2, type: "qq", typeId: "1426995762", srcImg: "qq_img.png" },
        { id: 3, type: "weixing", typeId: "15579067806", srcImg: "weixin_img.jpg" },
        { id: 4, type: "mail", typeId: "gstel15579067806@163.com", srcImg: "" }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
@import '~@/styles/var.less';
@import '~@/styles/global.less';
.test-container {
  padding: 200px;
  background: @dark;
}
</style>