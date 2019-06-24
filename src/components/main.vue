<template>
  <el-container>
    <el-header>
      <el-menu
        :default-active="activeIndex"
        mode="horizontal"
        @select="handleSelect"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
      >
        <el-menu-item index="1">首&nbsp;&nbsp;&nbsp;&nbsp;页</el-menu-item>
        <el-submenu index="2">
          <template slot="title">我的工作台</template>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
          <el-menu-item index="2-3">选项3</el-menu-item>
          <el-submenu index="2-4">
            <template slot="title">选项4</template>
            <el-menu-item index="2-4-1">选项1</el-menu-item>
            <el-menu-item index="2-4-2">选项2</el-menu-item>
            <el-menu-item index="2-4-3">选项3</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-menu-item index="3">消息中心</el-menu-item>
        <el-menu-item index="4">
          订单管理
        </el-menu-item>
      </el-menu>
    </el-header>
    <el-main>
      <div class="block">
        <el-timeline>
          <el-timeline-item
            v-for="(activity, index) in activities"
            :key="index"
            :icon="activity.icon"
            :type="activity.type"
            :color="activity.color"
            :size="activity.size"
            :timestamp="activity.timestamp"
          >{{activity.content}}</el-timeline-item>
        </el-timeline>
      </div>
    </el-main>
    <el-footer>Powered By zmy</el-footer>
  </el-container>
</template>
<script>
export default {
  props: {
    user_id: String
  },
  data: function() {
    return {
      msg: this.$route.params.user_id,
      activeIndex: "1",
      activities: [{
          content: '支持使用图标',
          timestamp: '2018-04-12 20:46',
          size: 'large',
          type: 'primary',
          icon: 'el-icon-more'
        }, {
          content: '支持自定义颜色',
          timestamp: '2018-04-03 20:46',
          color: '#0bbd87'
        }, {
          content: '支持自定义尺寸',
          timestamp: '2018-04-03 20:46',
          size: 'large',
          color: '#999'
        }, {
          content: '默认样式的节点',
          timestamp: '2018-04-03 20:46',
          color: '#999'
        }]
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      this.$message(key+"::"+keyPath);
    }
  }
};
</script>
<style scoped>
.el-container {
  height: 100vh;
}
img {
  width: 20px;
  height: 20px;
}
.el-header {
  background-color: rgb(84, 92, 100);
  color: #333;
  text-align: center;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.el-footer {
  background-color: #b3c0d1;
  color: #333;
  height: 23px !important;
  margin-bottom: 0;
  text-align: center;
}
.block{
    border: 1px solid #999;
    width: 300px;
    padding: 20px;
    border-radius: 5px;
}
</style>

