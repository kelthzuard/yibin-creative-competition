<template>
<div>
    <Card>
        <span class="title">生产计划管理</span>
    </Card>
    <Card>
        <div>
            <Button type="primary" size="large">新建生产计划</Button>
        </div>
    </Card>
    <Card>
        <Table :columns="columns" :data="result"></Table>
    </Card>
</div>
</template>
<script>
export default {
  name: 'produceOrder',
  data () {
    return {
      columns: [
        {
          title: '计划名',
          key: 'name'
        },
        {
          title: '生产开始时间',
          key: 'start'
        },
        {
          title: '生产结束时间',
          key: 'end'
        },
        {
          title: '生产原料投入',
          key: 'stuff'
        },
        {
          title: '生产人力安排',
          key: 'people'
        },
        {
          title: '每日生产量',
          key: 'daily'
        },
        {
          title: '操作',
          render: (h, params) => {
            return h('div', [
              h('Button', {
                props: {
                  type: 'primary'
                },
                style: {
                  margin: '0 10px'
                }
              }, '修改'),
              h('Button', {
                props: {
                  type: 'error'
                }
              }, '删除')
            ])
          }
        }
      ],
      result: [
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        },
        {
          name: '织线生产',
          start: '2018/02/03',
          end: '2018/04/03',
          stuff: '500(箱)',
          people: '30(人/日)',
          daily: '300(份)'
        }
      ]
    }
  }
}
</script>
<style lang="less">
.title{
    font-size: 24px;
    font-weight: 600;
}
</style>
