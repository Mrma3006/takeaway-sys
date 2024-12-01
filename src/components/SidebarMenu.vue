<template>
    <el-menu default-active="1" class="el-menu-vertical-demo">
      <el-sub-menu index="1">
        <template #title>菜单项 1</template>
        <el-menu-item index="1-1">子菜单 1-1</el-menu-item>
        <el-menu-item index="1-2">子菜单 1-2</el-menu-item>
      </el-sub-menu>
      <el-menu-item index="2">菜单项 2</el-menu-item>
      <el-menu-item index="3">菜单项 3</el-menu-item>
    </el-menu>
  </template>
  
  <script>
  export default {
    name: 'SidebarMenu',
  };
  </script>