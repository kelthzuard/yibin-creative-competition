<template>
  <div>
    <Card>
      <div class="title">
        生产计划智能化推荐
      </div>
    </Card>
    <Card>
      <div class="Button">
        <Button type="primary" :size="buttonSize">一键导入订单</Button>
      </div>
      <Form :label-width="100">
        <FormItem label="订单名:">
          <Input></Input>
        </FormItem>
        <FormItem label="订单收入:">
          <InputNumber></InputNumber>
        </FormItem>
        <FormItem label="生产周期:">
          <Row>
              <Col span="4">
                  <DatePicker type="date" placeholder="开始时间"></DatePicker>
              </Col>
              <Col span="2" style="text-align: center">---------</Col>
              <Col span="4">
                  <TimePicker type="time" placeholder="结束时间"></TimePicker>
              </Col>
          </Row>
        </FormItem>
        <FormItem label="生产原料需求:">
          <div>
            <Button type="primary">导入EXCEL</Button>
          </div>
        </FormItem>
        <FormItem label="供应商选择:">
            <RadioGroup>
                <Radio label="male">供应商A</Radio>
                <Radio label="male">供应商B</Radio>
                <Radio label="male">供应商C</Radio>
                <Radio label="male">供应商D</Radio>
                <Radio label="male">供应商E</Radio>
            </RadioGroup>
        </FormItem>
        <FormItem label="人力分配">
            <Slider v-model="slider" range></Slider>
        </FormItem>
        <FormItem>
            <Button type="primary">生成成本与收益预测</Button>
            <Button style="margin-left: 8px">保存</Button>
        </FormItem>
      </Form>
    </Card>
    <Modal
        v-model="modal1"
        title="生产预测结果"
        @on-ok="ok"
        @on-cancel="cancel"
        width="600">
        <div class="modal">
          <p class="modal-title">生产决策预测结果:</p>
          <div>
            <Button type="primary" class="button">导出生产计划EXCEL</Button>
            <Button type="primary" class="button">一键部署</Button>
          </div>
          <p class="modal-title">各个方案收益预测曲线:</p>
          <example style="height: 310px;"/>
        </div>
    </Modal>
  </div>
</template>
<script>
import Example from './example.vue'
export default {
  name: 'order',
  data () {
    return {
      buttonSize: 'large',
      slider: [0, 20],
      modal1: true
    }
  },
  components: {
    Example
  },
  methods: {
    ok () {
      this.$Message.info('Clicked ok')
    },
    cancel () {
      this.$Message.info('Clicked cancel')
    }
  }
}
</script>
<style lang="less">
.Button{
  margin: 10px 20px;
}
.title{
    font-size: 24px;
    font-weight: 600;
}
.modal{
  padding: 20px;
  box-sizing: border-box;
  .modal-title{
    font-size: 24px;
    font-weight: 600;
    margin: 20px 0;
  }
  .button{
    margin: 0 20px 20px 0;
  }
}
</style>
