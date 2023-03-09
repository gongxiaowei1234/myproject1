<template>
  <div>
    <el-card>
      <div class="header">
        <div class="category-header">
          <span>销售额类别占比</span>
          <el-radio-group v-model="value">
            <el-radio-button label="全部渠道"></el-radio-button>
            <el-radio-button label="线上"></el-radio-button>
            <el-radio-button label="门店"></el-radio-button>
          </el-radio-group>
        </div>
        <div class="charts2" ref="charts"></div>
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: "",
  data() {
    return {
      value: "全部渠道",
    };
  },
  created() {},
  methods: {},
  mounted() {
    // 第二步 初始化图表实例
    let lineCharts = this.$echarts.init(this.$refs.charts);
    lineCharts.setOption({
      title: {
        text: "视频",
        subtext: 1048,
        left:"center",
        top:"center"
      },
      tooltip: {
        trigger: "item",
      },
      legend: {
        top: "5%",
        left: "center",
      },
      series: [
        {
          name: "Access From",
          type: "pie",
          radius: ["40%", "70%"],
          avoidLabelOverlap: false,
          itemStyle: {
            borderRadius: 10,
            borderColor: "#fff",
            borderWidth: 2,
          },
          //   文本位置
          label: {
            show: false,
            position: "outsize",
          },
          // 放大效果
          //   emphasis: {
          //     label: {
          //       show: true,
          //       fontSize: 40,
          //       fontWeight: 'bold'
          //     }
          //   },
          // labelLine 变为lable才显示引导线
          label: {
            show: true,
          },
          data: [
            { value: 1048, name: "视频" },
            { value: 735, name: "Direct" },
            { value: 580, name: "Email" },
            { value: 484, name: "Union Ads" },
            { value: 300, name: "Video Ads" },
          ],
        },
      ],
    });
    // 绑定事件
    // lineCharts.on('mouseover',  (params)=>{
    //     const{name,value} =params.data
    //     // 重新设置标题
    //     lineCharts.setOption({
    //         title:{
    //             text:'name',
    //             subtext:'value'
    //         }
    //     })

    // });
  },
};
</script>

<style>
.category-header {
  display: flex;
  justify-content: space-between;
  /* 显示在一条线上 */
  align-items: center;
}
.header {
  border-bottom: 1px solid #eee;
}
.charts2 {
  width: 100%;
  height: 300px;
}
</style>