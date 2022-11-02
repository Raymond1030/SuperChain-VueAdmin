<template>
  <div class="fill">
    <el-row :gutter="20" class="HomeOther">
      <el-col :span="10">
        <el-input v-model="chain_text" placeholder="请输入上链文本"></el-input>
      </el-col>
      <el-col :span="2">
        <el-button type="primary" size="medium" icon="el-icon-upload" @click="submit">提交</el-button>
      </el-col>
      <el-col :span="2">
        <el-button @click="drawer = true" type="info" size="medium" >查看终端</el-button>
      </el-col>
    </el-row>
    <el-row style="background:#fff;padding:8px 8px 0;margin-bottom:16px;">
      <line-chart :chart-data="lineChartData" />
    </el-row>
    <el-row :gutter="20" class="HomeData">
      <el-col :span="20">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <a :href="github" target="_blank">
              <icon-svg icon-class="iconGithub" />
            </a>
            <span>上链过程：</span>
          </div>
          <div class="logArea el-scrollbar">
            <div class="logContent">
              <p class="title">更新内容：</p>
            </div>
          </div>
        </el-card>
      </el-col>
    </el-row>
    <el-drawer title="终端" :visible.sync="drawer" class="drawer_style">
      <span style="color:#fff">打印日志</span>
    </el-drawer>
  </div>

</template>


<script>
import { mapGetters } from 'vuex'

export default {
  name: 'User',
  data() {
    return {
      chain_text: "",
      count: 0,
      drawer: false,
    }
  },
  methods: {
    submit() {
      this.$message({
        message: '提交成功',
        type: 'success'
      });
    },
    load() {
      this.count += 2
    }
  },
  computed: {
    ...mapGetters(['name'])
  }
}
</script>


<style lang="scss" scoped>

.drawer_style {
        ::v-deep  .el-drawer.rtl  {
          background: #121212 !important;
            }
        ::v-deep .el-drawer__header {
                color: #ffffff;
                font-size: 18px;
            }
    }

.HomeData {

  //设置display为flex
  display: flex;
  //设置左右居中
  justify-content: left;
  //设置上下居中
  align-items: center;
}

.HomeOther {
  //设置display为flex
  display: flex;
  //设置左右居中
  justify-content: left;
  //设置上下居中
  align-items: center;
}


.fill {
  padding: 80px;
  box-sizing: border-box;
}
.el-drawer.rtl {
    background: #6aabc5;
  }

.logArea {
  overflow: auto;
  height: 100%;
}
</style>