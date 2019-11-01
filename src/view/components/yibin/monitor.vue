<template>
<div>
    <Card>
        <div class="title">
            智能监控系统
        </div>
        <span>黑色代表机器处于正常状态</span><br>
        <span style="color: #f9f494">黄色</span><span>代表机器处于隐患出错状态</span><br>
        <span style="color: #d81e06">红色</span><span>代表机器已经发生错误，请及时检修</span>
    </Card>
    <div v-for="(item, index) in monitorList" :key="index">
        <Card>
            <span class="label">{{index + 1}}号车间</span>
            <div>
                <div v-for="(Item, Index) in item" :key="Index" class="specific">
                    <img v-if="Item==0" src="@/assets/images/yibin/normal.png">
                    <img v-if="Item==1" src="@/assets/images/yibin/warning.png">
                    <img v-if="Item==2" src="@/assets/images/yibin/error.png">
                    <div class="name">{{Index + 1}}号机器</div>
                </div>
            </div>
        </Card>
    </div>
    <Card>
    </Card>
</div>
</template>
<script>
export default {
  name: 'monitor',
  data () {
    return {
      monitorList: [
        [0, 0, 0, 1, 2, 0, 0, 0],
        [2, 2, 0, 0, 0, 1, 0],
        [1, 1, 0, 0, 0, 2, 0, 0, 1],
        [1, 0, 0, 1, 2, 0]
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
.label{
    font-size: 18px;
    font-weight: 600;
    margin-left: 30px;
}
.specific{
    display: inline-block !important;
    img{
        width: 60px;
        margin: 10px 40px;
    }
    .name{
        text-align: center;
    }
}
</style>
