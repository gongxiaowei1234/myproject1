<template>
  <div>
    <el-card>
      <div class="header">
        <div class="search_header">
          <span>线上热门搜索</span>

          <el-dropdown>
            <span class="el-dropdown-link">
              <i class="el-icon-more"></i>
            </span>
            <el-dropdown-menu>
              <el-dropdown-item>黄金糕</el-dropdown-item>
              <el-dropdown-item>狮子头</el-dropdown-item>
              <el-dropdown-item>螺蛳粉</el-dropdown-item>
              <el-dropdown-item>双皮奶</el-dropdown-item>
              <el-dropdown-item>蚵仔煎</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </div>
      <div>
        <el-row :gutter="10">
          <el-col :span="12"> <lineCharts></lineCharts></el-col>
          <el-col :span="12"> <lineCharts></lineCharts></el-col>
        </el-row>
        <!-- :default-sort="{ prop: 'date', order: 'descending' }" -->
        <el-table :data="tableData" style="width: 100%" border>
          <el-table-column type="index" label="排名" width="80">
          </el-table-column>
          <el-table-column prop="name" label="搜搜关键字" width="180">
          </el-table-column>
          <!-- :formatter="formatter" -->
          <el-table-column prop="address" label="用户数" sortable>
          </el-table-column>
          <el-table-column prop="address" label="周涨幅" sortable>
          </el-table-column>
        </el-table>
        <el-pagination layout="prev, pager, next" :total="1000" class="pagination">
        </el-pagination>
      </div>
    </el-card>
  </div>
</template>

<script>
import lineCharts from "./lineChart";
export default {
  name: "",
  components: { lineCharts },
  data() {
    return {
      tableData: [{}],
    };
  },
  created() {},
  methods: {},
  mounted() {},
};
</script>

<style>
.header {
  border-bottom: 1px solid rgb(220, 220, 214);
  margin: 5px 5px;
}
.search_header {
  display: flex;
  /*两个元素之间间隔相等 */
  justify-content: space-between;
  margin-bottom: 5px;
}
.pagination{
  float: right;
}
</style>