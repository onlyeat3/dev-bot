<template>
  <a-layout id="app" style="min-height: 100vh">
    <a-layout-sider v-model="collapsed" style="background-color: #fff">
      <div class="logo" />
      <a-menu :default-selected-keys="['0']" mode="inline">
        <a-menu-item key="0">
          <router-link to="/">
            <a-icon type="home" />
            <span>Home</span>
          </router-link>
        </a-menu-item>

        <a-menu-item key="1">
          <router-link to="/python">
            <a-icon type="pie-chart" />
            <span> Python </span>
          </router-link>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <!-- <a-layout-header style="background: #fff" /> -->
      <a-layout-content>
        <a-card>
          <keep-alive>
            <router-view />
          </keep-alive>
        </a-card>
      </a-layout-content>
      <a-layout-footer style="text-align: center">
        Ant Design ©2018 Created by Ant UED
      </a-layout-footer>
    </a-layout>
  </a-layout>
</template>
<script>
export default {
  data () {
    return {
      collapsed: false,
    };
  },
};
</script>

<style>
#app .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}
</style>