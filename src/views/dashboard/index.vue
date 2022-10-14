<template>
  <el-container>
    <el-header>监控链场景下的区块链节点行为演示</el-header>
    <el-row :gutter="20" class="HomeData">
      <!-- <el-col :span="6"><div class="grid-content bg-purple">业务链节点数：</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">监控链节点数：</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">服务器负载：</div></el-col>
      <el-col :span="6"><div class="grid-content bg-purple">响应速度：</div></el-col> -->
      <el-col :span="5">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            业务链节点数
          </div>
          <div class="Card-data">XXX</div>
        </el-card>
      </el-col>
      <el-col :span="5">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            监控链节点数
          </div>
          <div class="Card-data">YYY</div>
        </el-card>
      </el-col>
      <el-col :span="5">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            服务器负载
          </div>
          <div class="Card-data">ZZZ</div>
        </el-card>
      </el-col>
      <el-col :span="5">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            响应速度
          </div>
          <div class="Card-data">ZZ ms</div>
        </el-card>
      </el-col>
    </el-row>
    <el-row style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">
      <line-chart :chart-data="lineChartData" />
    </el-row>
    <el-row :gutter="20" class="HomeOther">
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            系统日志
          </div>
          <div class="Card-data">XXXXXXXXXXXXXXXXXXXXXXXXXXXXX</div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="CardHeader">
            其他一些统计数据
          </div>
          <div class="Card-data">XXXXXXXXXXXXXXXXXXXXXXXXXXXXX</div>
        </el-card>
      </el-col>
    </el-row>
  </el-container>
  <!-- <div class="dashboard-container">
    <div class="board-header">监控链场景下的区块链节点行为演示</div>
    <div class="board-data">业务链节点数：</div>
    <div class="board-data">监控链节点数：</div>
    <div class="board-data">服务器负载：</div>
    <div class="board-data">响应速度：</div>
    <div class="board-data">响应速度：</div> -->
  <!-- <div class="dashboard-text">name: {{ name }}</div> -->
  <!-- </div> -->
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters(['name'])
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }

  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}

.HomeData {

  //设置display为flex
  display: flex;
  //设置左右居中
  justify-content: center;
  //设置上下居中
  align-items: center;
}
.HomeOther
{
    //设置display为flex
    display: flex;
  //设置左右居中
  justify-content: center;
  //设置上下居中
  align-items: center;
}
.el-header {
  // width: 300px;
  // height: 400px;
  // top: 50%;
  // left: 50%;
  //  margin-left: -300px;
  // margin-top: -200px;
  margin: 30px;
  text-align: center;
}

.el-row {
  margin-bottom: 20px;
  left: 15px;

  // margin-right: 15px;
  &:last-child {
    margin-bottom: 0;
  }
}

.el-col {
  border-radius: 7px;
}

.CardHeader {
  text-align: center;
}

.Card-data {
  text-align: center;
}

// .bg-purple-dark {
//   background: #99a9bf;
// }
// .bg-purple {
//   background: #d3dce6;
// }
// .bg-purple-light {
//   background: #e5e9f2;
// }
// .grid-content {
//   border-radius: 1px;
//   min-height: 36px;
//   text-align: center;
//   padding-top: 5px;
// }
// .row-bg {
//   padding: 10px 0;
//   background-color: #f9fafc;
// }
</style>
