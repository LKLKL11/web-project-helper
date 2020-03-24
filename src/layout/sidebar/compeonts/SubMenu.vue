<template>
  <div>
    <template v-for="(menu, index) in menus">
      <el-submenu v-if="menu.children && menu.children.length" :index="menu.index" :key="index">
        <submenu :menus="menu.children"></submenu>
      </el-submenu>
      <el-menu-item :index="menu.index" :key="index">{{menu.name}}</el-menu-item>
    </template>
  </div>
</template>

<script>
export default {
  name: 'SubMenu',
  props: {
    menus: {
      type: Array,
      default: () => ([]),
    },
  },
};
</script>

<style>

</style>
