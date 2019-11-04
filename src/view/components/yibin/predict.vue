<template>
    <div>
        <Card>
            <span class="title">模型选择:</span>
            <Card>
                <RadioGroup>
                    <Radio class="radio">一元线性回归</Radio>
                    <Radio class="radio">多元线性回归</Radio>
                    <Radio class="radio">朴素贝叶斯</Radio>
                    <Radio class="radio">支持向量机</Radio>
                    <Radio class="radio">随机森林</Radio>
                </RadioGroup>
            </Card>
        </Card>
        <Card>
            <span class="title">参数选择:</span>
            <Card>
                <Row class="row">
                    <Col span="2" class="subTitle">选择时间区间：</Col>
                    <Col span="3">
                        <DatePicker type="date" placeholder="开始时间"></DatePicker>
                    </Col>
                    <Col span="1" style="text-align: center">---------</Col>
                    <Col span="4">
                        <TimePicker type="time" placeholder="结束时间"></TimePicker>
                    </Col>
                </Row>
                <Row class="row">
                    <Col span="2">
                        <span class="subTitle">预测结果:</span>
                    </COl>
                    <Col>
                        <CheckboxGroup>
                            <Checkbox class="check">
                                <span>纱线平均生产成本</span>
                            </Checkbox>
                            <Checkbox class="check">
                                <span>纱线销售平均价格</span>
                            </Checkbox>
                            <Checkbox class="check">
                                <span>织物加工平均成本</span>
                            </Checkbox>
                            <Checkbox class="check">
                                <span>织物销售平均价格</span>
                            </Checkbox >
                            <Checkbox class="check">
                                <span>织物平均销售量</span>
                            </Checkbox>
                            <Checkbox class="check">
                                <span>物流仓储平均成本</span>
                            </Checkbox>
                        </CheckboxGroup>
                    </Col>
                </Row>
                <Button type="primary">生成预测结果</Button>
            </Card>
        </Card>
        <Card>
            <span class="title">输出结果：</span>
            <Card style="display: flex">
                <div class="inlineBlock">
                    <Table :columns="columns" :data="resultData" width="550"></Table>
                </div>
                <div class="inlineBlock">
                    <div>
                        <example style="height: 250px;width: 700px"/>
                    </div>
                    <div>
                        <span class="title">预测结果：</span>
                        <Table :columns="columns" :data="resultDataPredict" width="550"></Table>
                    </div>
                </div>
            </Card>
        </Card>
    </div>
</template>
<script>
import Example from './predict-col.vue'
export default {
  name: 'predict',
  components: {
    Example
  },
  data () {
    return {
      columns: [
        {
          title: '时间',
          key: 'time'
        },
        {
          title: '纱线平均价格',
          key: 'price'
        },
        {
          title: '纱线平均生产成本',
          key: 'cost'
        },
        {
          title: '物流仓储平均成本',
          key: 'transform'
        }
      ],
      resultDataPredict: [
        {
          time: '2020/01',
          price: '25',
          cost: '20',
          transform: '3'
        },
        {
          time: '2020/02',
          price: '24',
          cost: '19',
          transform: '4'
        }
      ],
      resultData: [
        {
          time: '2019/01',
          price: '20',
          cost: '18',
          transform: '3'
        },
        {
          time: '2019/02',
          price: '22',
          cost: '19',
          transform: '3'
        },
        {
          time: '2019/03',
          price: '23',
          cost: '19',
          transform: '4'
        },
        {
          time: '2019/04',
          price: '24',
          cost: '20',
          transform: '4'
        },
        {
          time: '2019/05',
          price: '22',
          cost: '18',
          transform: '3'
        },
        {
          time: '2019/06',
          price: '21',
          cost: '17',
          transform: '3'
        },
        {
          time: '2019/08',
          price: '20',
          cost: '18',
          transform: '3'
        },
        {
          time: '2019/09',
          price: '21',
          cost: '19',
          transform: '4'
        }
      ]
    }
  }
}
</script>
<style lang="less">
.title{
    font-size: 22px;
    font-weight: 600;
    margin: 10px 20px;
}
.row{
    margin: 20px 0;
}
.radio{
    margin: 0 10px;
    font-size: 16px;
}
.subTitle{
    font-size: 18px;
}
.check{
    height: 30px;
    line-height: 30px;
    font-size: 16px;
}
.inlineBlock{
    display: inline-block;
    vertical-align: top;
    height: 500px;
    margin: 0 20px;
}
</style>
