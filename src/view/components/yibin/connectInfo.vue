<template>
<div>
    <Card>
        <span class="title">生产任务管理</span>
    </Card>
    <Card>
        <div class="title">我的任务（车间主任）</div>
        <div>
            <Card v-for="(item, index) in task" :key="index" class="task">
                <div>任务名: {{item.name}}</div>
                <div>开始时间: {{item.start}}</div>
                <div>结束时间: {{item.end}}</div>
                <div>工作地点: {{item.postion}}</div>
                <div>所属职位: {{item.stuff}}</div>
                <div>任务进度: {{item.percent}}</div>
                <Button type="primary">查看详情</Button>
                <div style="display: inline-block;margin-left: 10px;">
                    <Button type="success">修改任务进度</Button>
                </div>
            </Card>
        </div>
    </Card>
</div>
</template>
<script>
export default {
  name: 'connectInfo',
  data () {
    return {
      task: [
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        },
        {
          name: '纺线生产',
          start: '2018/03/02',
          end: '2018/05/02',
          position: '一号车间',
          stuff: '车间主任',
          percent: '100%（已完成)'
        }
      ]
    }
  }
}
</script>
<style lang="less">
.task{
    display: inline-block;
    width: 30%;
    margin: 1%;
    font-size: 18px;
}
.title{
    font-size: 24px;
    font-weight: 600;
}
</style>
