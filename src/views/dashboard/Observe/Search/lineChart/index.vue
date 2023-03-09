<template>
  <div>
    <div class="header1">
      <span class="search-header">搜索用户数</span>
      <i class="el-icon-info"></i>
    </div>
    <div class="main1">
      <span class="main-title">12321</span>
      <span class="main-content">17.1
        <i class="el-icon-caret-top"></i>
        <i class="el-icon-caret-bottom"></i>
      </span>
    </div>
    <div class="footer">
      <div class="charts" ref="charts"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {};
  },
  created() {},
  methods: {},
  mounted() {
    // 第二步 初始化图表实例
    let lineCharts = this.$echarts.init(this.$refs.charts);
    // 第三步 配置数据
    lineCharts.setOption({
      tooltip: {},
      // x轴数据设置
      xAxis: {
        // 隐藏x轴
        show: false,
        type: "category",
      },
      yAxis: {
        //  隐藏x轴
        show: false,
      },
      // 设置图表类型，图表数据
      series: [
        {
        //   name: "销量",
          // bar 柱状图  line折线图 pie 饼图
          type: "line",
          // 线段为光滑曲线
          smooth: true,
          // 拐点样式的设置
          itemStyle: {
            // 透明度
            opacity: 0,
          },
          //   线条的样式
          lineStyle: {
            color: "blue",
          },
          // 填充颜色设置
          areaStyle: {
            // 线性渐变色
            color: {
              type: "linear",
              x: 0,
              y: 0,
              x2: 0,
              y2: 1,
              colorStops: [
                {
                  offset: 0,
                  color: "blue", // 0% 处的颜色
                },
                {
                  offset: 1,
                  color: " #fff", // 100% 处的颜色
                },
              ],
            },
          },
          data: [10, 20, 15,35, 30, 10, 15, 5, 20],
        },
      ],
      // 布局
      grid: {
        left: 0,
        top: 0,
        right: 0,
        bottom: 10,
      },
    });
  },
};
</script>

<style>
.main1{
  margin: 10px 0px;
}
.header1{
  display: flex;
  align-items: center;

}
.search-header{
  margin-right:20px;
}
.el-icon-info{
  color: rgb(152, 152, 143);
}
.el-icon-caret-top{
  margin-left: 10px;
  color: red;
}
.main-title{
  margin-right: 30px;
}
.main-content{
  margin-right: 30px;
}
.el-icon-caret-bottom {
  color: rgb(51, 212, 33);
}
.charts{
  width: 100%;
  height: 50px;
}
</style>