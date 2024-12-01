<template>
  <el-container style="height: 100vh">
    <!-- 头部菜单栏 -->
    <el-header>
      <div class="header-content">
        <h1>外卖系统测试-管理界面</h1>
        <el-menu :default-active="activeMenu" mode="horizontal" @select="handleHeaderMenuSelect">
          <el-menu-item index="home">主页</el-menu-item>
          <el-menu-item index="about">关于</el-menu-item>
        </el-menu>
      </div>
    </el-header>

    <!-- 主界面 -->
    <el-container>
      <!-- 左侧菜单栏 -->
      <el-aside width="200px" class="sidebar">
        <el-menu :default-active="activeSidebar" @select="handleSidebarSelect">
          <el-menu-item index="menu1">工作台</el-menu-item>
          <el-menu-item index="menu2">数据统计</el-menu-item>
          <el-menu-item index="menu3">订单管理</el-menu-item>
          <el-menu-item index="menu4">套餐管理</el-menu-item>
          <el-menu-item index="menu5">菜品管理</el-menu-item>
          <el-menu-item index="menu6">分类管理</el-menu-item>
          <el-menu-item index="menu7">员工管理</el-menu-item>
        </el-menu>
      </el-aside>

      <!-- 头部菜单选项 -->
      <el-main>
        <div v-if="currentPage === 'home'">
          <img src="https://via.placeholder.com/600x400" alt="主页图片" />
        </div>
        <div v-if="currentPage === 'about'">
          <img src="https://via.placeholder.com/600x400?text=About" alt="关于图片" />
        </div>

        <!-- 工作台 -->
        <div v-if="currentPage === 'menu1'">
          <img src="https://via.placeholder.com/600x400?text=workspace" alt="工作台图片" />
        </div>
        <!-- 数据统计 -->
        <div v-if="currentPage === 'menu2'">
          <img src="https://via.placeholder.com/600x400?text=statistics" alt="数据统计图片" />
        </div>
        <!-- 订单管理 -->
        <div v-if="currentPage === 'menu3'">
          <img src="https://via.placeholder.com/600x400?text=orders" alt="订单管理图片" />
        </div>
        <!-- 套餐管理 -->
        <div v-if="currentPage === 'menu4'">
          <img src="https://via.placeholder.com/600x400?text=sets" alt="套餐管理图片" />
        </div>
        <!-- 菜品管理 -->
        <div v-if="currentPage === 'menu5'">
          <img src="https://via.placeholder.com/600x400?text=dishes" alt="菜品管理图片" />
        </div>
        <!-- 分类管理 -->
        <div v-if="currentPage === 'menu6'">
          <img src="https://via.placeholder.com/600x400?text=categories" alt="分类管理图片" />
        </div>
        <!-- 员工管理 -->
        <div v-if="currentPage === 'menu7'">
          <img src="https://via.placeholder.com/600x400?text=employees" alt="员工管理图片" />
        </div>
      </el-main>
    </el-container>

    <!-- Footer -->
    <el-footer class="footer">
      <div>© 2024 Company TakeawaySys-Test. <a href="https://www.example.com" target="_blank">测试URL</a></div>
    </el-footer>
  </el-container>
</template>

<script>
import { ref } from 'vue'
import { ElContainer, ElHeader, ElAside, ElMain, ElFooter, ElMenu, ElMenuItem } from 'element-plus'

export default {
  components: {
    ElContainer,
    ElHeader,
    ElAside,
    ElMain,
    ElFooter,
    ElMenu,
    ElMenuItem
  },
  setup() {
    const activeMenu = ref('home')
    const activeSidebar = ref('menu1')
    const currentPage = ref('home')

    // 头部菜单栏的点击事件
    const handleHeaderMenuSelect = (index) => {
      currentPage.value = index
      activeSidebar.value = false
    }

    // 左侧菜单栏的点击事件
    const handleSidebarSelect = (index) => {
      activeSidebar.value = index
      currentPage.value = index
    }

    return {
      activeMenu,
      activeSidebar,
      currentPage,
      handleHeaderMenuSelect,
      handleSidebarSelect
    }
  }
}
</script>

<style scoped>
/* 头部菜单栏 */
.header {
  background-color: #007bff; /* 头部颜色：蓝色 */
  color: white; /* 头部文本颜色：白色 */
}

/* 菜单栏选项按钮 */
.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}


/* 左侧菜单栏 */
.sidebar {
  background-color: #e0f7fa; /* 左侧菜单栏颜色：浅蓝色 */
  padding: 10px;
}

/* 底端样式 */
.footer {
  text-align: center;
  padding: 10px;
  background-color: #f1f1f1;
}

/* UI美化设计 */
/* 菜单项的常规样式 */
.el-menu-item {
  font-size: 16px;
}

/* 鼠标悬停时的菜单项背景色 */
.el-menu-item:hover {
  background-color: #b3e5fc; /* 鼠标悬停时颜色：浅蓝色 */
}

/* 选中状态下的菜单项背景色 */
.el-menu-item.is-active {
  background-color: #0288d1; /* 选中时颜色：深蓝色 */
  color: white; /* 选中项文字颜色：白色 */
}

.el-header .el-menu {
  border: none; /* 去掉菜单的边框 */
}
</style>