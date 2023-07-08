<template>
  <el-container style="height: 100%; border: 1px solid #eee">
    <el-aside
      :width="menuWidth + 'px'"
      style="background-color: rgb(238, 241, 246); overflow-x: hidden"
    >
      <el-menu
        :default-openeds="['1', '3']"
        :collapse="isCollapsed"
        :collapse-transition="false"
      >
        <el-submenu index="1">
          <template slot="title"
            ><i class="el-icon-message"></i><span slot="title">导航一</span></template
          >
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="1-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="1-4">
            <template slot="title">选项4</template>
            <el-menu-item index="1-4-1">选项4-1</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-submenu index="2">
          <template slot="title"
            ><i class="el-icon-menu"></i><span slot="title">导航二</span></template
          >
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="2-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="2-4">
            <template slot="title">选项4</template>
            <el-menu-item index="2-4-1">选项4-1</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title"
            ><i class="el-icon-setting"></i><span slot="title">导航三</span></template
          >
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="3-1">选项1</el-menu-item>
            <el-menu-item index="3-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="3-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="3-4">
            <template slot="title">选项4</template>
            <el-menu-item index="3-4-1">选项4-1</el-menu-item>
          </el-submenu>
        </el-submenu>
      </el-menu>
    </el-aside>

    <el-container>
      <el-header style="font-size: 12px; line-height: 60px; display: flex">
        <div style="flex: 1; text-align: left">
          <span style="font-size: 20px">
            <i
              :class="[isCollapsed ? 'el-icon-s-fold' : 'el-icon-s-unfold']"
              @click="collapse"
            ></i>
          </span>
        </div>
        <span>王小虎</span>
        <el-dropdown>
          <i class="el-icon-arrow-down" style="margin-right: 15px; cursor: pointer"></i>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>个人</el-dropdown-item>
            <el-dropdown-item>退出</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </el-header>

      <el-main>
        <el-table :data="tableData">
          <el-table-column prop="date" label="日期" width="140"> </el-table-column>
          <el-table-column prop="name" label="姓名" width="120"> </el-table-column>
          <el-table-column prop="address" label="地址"> </el-table-column>
        </el-table>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(10).fill(item),
      isCollapsed: false,
      menuWidth: 200
    }
  },
  methods: {
    collapse() {
      this.isCollapsed = !this.isCollapsed
      if (this.menuWidth == 200) {
        this.menuWidth = 50
      } else {
        this.menuWidth = 200
      }
    }
  }
}
</script>

<style>
.el-header {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}
</style>
