<template>
  <div id="c_Uncommitted_data" class="main" :class="{'isShow':show}">
    <main-header>
      <span slot="h3">未提交资料</span>
      <Button class="fr" size="large" @click="exportData(1)"> 导出数据</Button>
    </main-header>
    <section class="c_Uncommitted_list">
      <Table :columns="columns8" :data="data7" size="small" ref="table"></Table>
    </section>
  </div>
</template>
<script>
import mainHeader from '../../components/header/main_header.vue'
export default {
  components: { mainHeader },
  data() {
    return {
      columns8: [
        {
          "title": "名称",
          "key": "name",
          "fixed": "left",
          "width": 200
        },
        {
          "title": "展示",
          "key": "show",
          "width": 150,
          "sortable": true,
          filters: [
            {
              label: '大于4000',
              value: 1
            },
            {
              label: '小于4000',
              value: 2
            }
          ],
          filterMultiple: false,
          filterMethod(value, row) {
            if (value === 1) {
              return row.show > 4000;
            } else if (value === 2) {
              return row.show < 4000;
            }
          }
        },
        {
          "title": "唤醒",
          "key": "weak",
          "width": 150,
          "sortable": true
        },
        {
          "title": "登录",
          "key": "signin",
          "width": 150,
          "sortable": true
        },
        {
          "title": "点击",
          "key": "click",
          "width": 150,
          "sortable": true
        },
        {
          "title": "激活",
          "key": "active",
          "width": 150,
          "sortable": true
        },
        {
          "title": "7日留存",
          "key": "day7",
          "width": 150,
          "sortable": true
        },

      ],
      data7: [
        {
          "name": "推广名称1",
          "fav": 0,
          "show": 7302,
          "weak": 5627,
          "signin": 1563,
          "click": 4254,
          "active": 1438,
          "day7": 274,
          "day30": 285,
          "tomorrow": 1727,
          "day": 558,
          "week": 4440,
          "month": 5610
        },
        {
          "name": "推广名称2",
          "fav": 0,
          "show": 4720,
          "weak": 4086,
          "signin": 3792,
          "click": 8690,
          "active": 8470,
          "day7": 8172,
          "day30": 5197,
          "tomorrow": 1684,
          "day": 2593,
          "week": 2507,
          "month": 1537
        },
        {
          "name": "推广名称3",
          "fav": 0,
          "show": 7181,
          "weak": 8007,
          "signin": 8477,
          "click": 1879,
          "active": 16,
          "day7": 2249,
          "day30": 3450,
          "tomorrow": 377,
          "day": 1561,
          "week": 3219,
          "month": 1588
        },
        {
          "name": "推广名称4",
          "fav": 0,
          "show": 9911,
          "weak": 8976,
          "signin": 8807,
          "click": 8050,
          "active": 7668,
          "day7": 1547,
          "day30": 2357,
          "tomorrow": 7278,
          "day": 5309,
          "week": 1655,
          "month": 9043
        },
        {
          "name": "推广名称5",
          "fav": 0,
          "show": 934,
          "weak": 1394,
          "signin": 6463,
          "click": 5278,
          "active": 9256,
          "day7": 209,
          "day30": 3563,
          "tomorrow": 8285,
          "day": 1230,
          "week": 4840,
          "month": 9908
        },
        {
          "name": "推广名称6",
          "fav": 0,
          "show": 6856,
          "weak": 1608,
          "signin": 457,
          "click": 4949,
          "active": 2909,
          "day7": 4525,
          "day30": 6171,
          "tomorrow": 1920,
          "day": 1966,
          "week": 904,
          "month": 6851
        },
        {
          "name": "推广名称7",
          "fav": 0,
          "show": 5107,
          "weak": 6407,
          "signin": 4166,
          "click": 7970,
          "active": 1002,
          "day7": 8701,
          "day30": 9040,
          "tomorrow": 7632,
          "day": 4061,
          "week": 4359,
          "month": 3676
        },
        {
          "name": "推广名称8",
          "fav": 0,
          "show": 862,
          "weak": 6520,
          "signin": 6696,
          "click": 3209,
          "active": 6801,
          "day7": 6364,
          "day30": 6850,
          "tomorrow": 9408,
          "day": 2481,
          "week": 1479,
          "month": 2346
        },
        {
          "name": "推广名称9",
          "fav": 0,
          "show": 567,
          "weak": 5859,
          "signin": 128,
          "click": 6593,
          "active": 1971,
          "day7": 7596,
          "day30": 3546,
          "tomorrow": 6641,
          "day": 1611,
          "week": 5534,
          "month": 3190
        },
        {
          "name": "推广名称10",
          "fav": 0,
          "show": 3651,
          "weak": 1819,
          "signin": 4595,
          "click": 7499,
          "active": 7405,
          "day7": 8710,
          "day30": 5518,
          "tomorrow": 428,
          "day": 9768,
          "week": 2864,
          "month": 5811
        }
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
    },
    exportData(type) {
      if (type === 1) {
        this.$refs.table.exportCsv({
          filename: '原始数据'
        });
      }
    }
  }
}
</script>
<style lang="less" scoped>
#c_Uncommitted_data {
  .c_Uncommitted_list {
    margin-top: 10px;
  }
}
</style>
