<template>
  <div id="roleinfo" class="main" :class="{'isShow':show}">
    <main-header>
      <span slot="h3">查看</span>
    </main-header>
    <section style="text-align: left;padding: 20px 0;">
      <span style="font-size: 16px">角色：</span>
      <Select v-model="model1" style="width:150px">
        <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
      </Select>
    </section>
    <section style="text-align: left" class="clearfix">
      <Checkbox style="font-size: 18px;line-height: 40px;">订单管理</Checkbox>
      <ul>
        <li v-for="item in 5" style="text-align: center;line-height: ;">
          <Checkbox style="font-size: 14px;">查看</Checkbox>
          <Checkbox style="font-size: 14px;">指派</Checkbox>
        </li>
      </ul>
    </section>
    <section style="text-align: left" class="clearfix">
      <Checkbox style="font-size: 18px;line-height: 40px;">骑士管理</Checkbox>
      <ul>
        <li v-for="item in 10">
          <Checkbox style="font-size: 14px;">未提交资料</Checkbox>
        </li>
      </ul>
    </section>
    <section style="text-align: left" class="clearfix">
      <Checkbox style="font-size: 18px;line-height: 40px;">配置设置</Checkbox>
      <ul>
        <li v-for="item in 10">
          <Checkbox style="font-size: 14px;">查看</Checkbox>
          <Checkbox style="font-size: 14px;">新增</Checkbox>
        </li>
      </ul>
    </section>
    <section style="text-align: left" class="clearfix">
      <Checkbox style="font-size: 18px;line-height: 40px;">数据中心</Checkbox>
      <ul>
        <li v-for="item in 10">
          <Checkbox style="font-size: 14px;">配送员数据</Checkbox>
          <Checkbox style="font-size: 14px;">指派</Checkbox>
        </li>
      </ul>
    </section>
  </div>
</template>
<script>
import mainHeader from '../../components/header/main_header.vue'
export default {
  components: { mainHeader },
  data() {
    return {
      model1: '',
      cityList: [
        {
          value: 'quzhang',
          label: '区长'
        },
        {
          value: 'zhanzhang',
          label: '站长'
        },
        {
          value: 'Administrators',
          label: '管理员'
        },
        {
          value: 'super_Administrators',
          label: '超级管理员'
        },
      ]

    }
  },
  computed: {
    show() {
      return this.$store.state.show
    }
  },
  methods: {
    getCurrentDate() {
      return new Date().toLocaleDateString()
    }
  }
}
</script>
<style lang="less" scoped>
#roleinfo {
  section {
    li {
      width: 220px;
      height: 61px;
      line-height: 61px;
      float: left;
      border: 1px solid #666666;
      margin-left: -1px;
      margin-top: -1px;
    }
  }
}
</style>
