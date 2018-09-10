<template>
  <div class="test">
    <Pie :size="'400px'" :rate='80' :bgColor="'yellow'" :rateBgColor="'green'">80%</Pie>
    <Pie :size="'300px'" :rate='60' :bgColor="'yellow'" :rateBgColor="'green'">60%</Pie>
    <Pie :size="'200px'" :rate='40' :bgColor="'yellow'" :rateBgColor="'green'">40%</Pie>
    <Pie :size="'100px'" :rate='20' :bgColor="'yellow'" :rateBgColor="'green'">20%</Pie>
  </div>
</template>

<script>
  import Pie from '@/components/PieChart';

  export default {
    name: 'test',
    data() {
      return {}
    },
    components: {
      Pie,
    },
    methods: {},
    mounted() {
    }
  }
</script>

<style type="text/less" lang="less" scoped>
  .test {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
