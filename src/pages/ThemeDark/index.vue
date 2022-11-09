<template>
  <div class="page">
    <div class="page-title">Dark 模式</div>
    <div class="main">
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-row style="margin-bottom: 10px">
            <el-button>默认按钮</el-button>
            <el-button type="primary">主要按钮</el-button>
            <el-button type="success">成功按钮</el-button>
            <el-button type="info">信息按钮</el-button>
            <el-button type="warning">警告按钮</el-button>
            <el-button type="danger">危险按钮</el-button>
          </el-row>

          <el-row style="margin-bottom: 10px">
            <el-button plain>朴素按钮</el-button>
            <el-button type="primary"
                       plain>主要按钮</el-button>
            <el-button type="success"
                       plain>成功按钮</el-button>
            <el-button type="info"
                       plain>信息按钮</el-button>
            <el-button type="warning"
                       plain>警告按钮</el-button>
            <el-button type="danger"
                       plain>危险按钮</el-button>
          </el-row>

          <el-row style="margin-bottom: 10px">
            <el-button round>圆角按钮</el-button>
            <el-button type="primary"
                       round>主要按钮</el-button>
            <el-button type="success"
                       round>成功按钮</el-button>
            <el-button type="info"
                       round>信息按钮</el-button>
            <el-button type="warning"
                       round>警告按钮</el-button>
            <el-button type="danger"
                       round>危险按钮</el-button>
          </el-row>

          <el-row style="margin-bottom: 10px">
            <el-button icon="el-icon-search"
                       circle></el-button>
            <el-button type="primary"
                       icon="el-icon-edit"
                       circle></el-button>
            <el-button type="success"
                       icon="el-icon-check"
                       circle></el-button>
            <el-button type="info"
                       icon="el-icon-message"
                       circle></el-button>
            <el-button type="warning"
                       icon="el-icon-star-off"
                       circle></el-button>
            <el-button type="danger"
                       icon="el-icon-delete"
                       circle></el-button>
          </el-row>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-form ref="form"
                   :model="form"
                   label-width="80px">
            <el-form-item label="活动名称">
              <el-input v-model="form.name"></el-input>
            </el-form-item>
            <el-form-item label="活动区域">
              <el-select v-model="form.region"
                         placeholder="请选择活动区域">
                <el-option label="区域一"
                           value="shanghai"></el-option>
                <el-option label="区域二"
                           value="beijing"></el-option>
              </el-select>
            </el-form-item>
            <el-form-item label="即时配送">
              <el-switch v-model="form.delivery"></el-switch>
            </el-form-item>
            <el-form-item label="活动性质">
              <el-checkbox-group v-model="form.type">
                <el-checkbox label="美食/餐厅线上活动"
                             name="type"></el-checkbox>
                <el-checkbox label="地推活动"
                             name="type"></el-checkbox>
                <el-checkbox label="线下主题活动"
                             name="type"></el-checkbox>
                <el-checkbox label="单纯品牌曝光"
                             name="type"></el-checkbox>
              </el-checkbox-group>
            </el-form-item>
            <el-form-item label="特殊资源">
              <el-radio-group v-model="form.resource">
                <el-radio label="线上品牌商赞助"></el-radio>
                <el-radio label="线下场地免费"></el-radio>
              </el-radio-group>
            </el-form-item>
            <el-form-item label="活动形式">
              <el-input type="textarea"
                        v-model="form.desc"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary">立即创建</el-button>
              <el-button>取消</el-button>
            </el-form-item>
          </el-form>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-table :data="tableData"
                    style="width: 100%">
            <el-table-column prop="date"
                             label="日期"
                             width="180">
            </el-table-column>
            <el-table-column prop="name"
                             label="姓名"
                             width="180">
            </el-table-column>
            <el-table-column prop="address"
                             label="地址">
            </el-table-column>
          </el-table>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-table v-loading="true"
                    :data="tableData"
                    style="width: 100%">
            <el-table-column prop="date"
                             label="日期"
                             width="180">
            </el-table-column>
            <el-table-column prop="name"
                             label="姓名"
                             width="180">
            </el-table-column>
            <el-table-column prop="address"
                             label="地址">
            </el-table-column>
          </el-table>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-dropdown>
            <el-button type="primary">
              更多菜单<i class="el-icon-arrow-down el-icon--right"></i>
            </el-button>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>黄金糕</el-dropdown-item>
              <el-dropdown-item>狮子头</el-dropdown-item>
              <el-dropdown-item>螺蛳粉</el-dropdown-item>
              <el-dropdown-item>双皮奶</el-dropdown-item>
              <el-dropdown-item>蚵仔煎</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown split-button
                       type="primary">
            更多菜单
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>黄金糕</el-dropdown-item>
              <el-dropdown-item>狮子头</el-dropdown-item>
              <el-dropdown-item>螺蛳粉</el-dropdown-item>
              <el-dropdown-item>双皮奶</el-dropdown-item>
              <el-dropdown-item>蚵仔煎</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-button type="text"
                     @click="dialogVisible = true">点击打开 Dialog</el-button>

          <el-dialog title="提示"
                     :visible.sync="dialogVisible"
                     width="30%">
            <span>这是一段信息</span>
            <span slot="footer"
                  class="dialog-footer">
              <el-button @click="dialogVisible = false">取 消</el-button>
              <el-button type="primary"
                         @click="dialogVisible = false">确 定</el-button>
            </span>
          </el-dialog>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-card class="box-card">
            <div slot="header"
                 class="clearfix">
              <span>卡片名称</span>
              <el-button style="float: right; padding: 3px 0"
                         type="text">操作按钮</el-button>
            </div>
            <div v-for="o in 4"
                 :key="o"
                 class="text item">
              {{ '列表内容 ' + o }}
            </div>
          </el-card>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-timeline>
            <el-timeline-item v-for="(activity, index) in activities"
                              :key="index"
                              :icon="activity.icon"
                              :type="activity.type"
                              :color="activity.color"
                              :size="activity.size"
                              :timestamp="activity.timestamp">
              {{ activity.content }}
            </el-timeline-item>
          </el-timeline>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="6"
                :offset="0">
          <el-switch v-model="switch1"
                     active-text="按月付费"
                     inactive-text="按年付费">
          </el-switch>
        </el-col>
        <el-col :span="6"
                :offset="0">
          <el-switch style="display: block"
                     v-model="switch2"
                     active-color="#13ce66"
                     inactive-color="#ff4949"
                     active-text="按月付费"
                     inactive-text="按年付费">
          </el-switch>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
          <el-slider v-model="sliderVal"
                     range
                     :marks="marks">
          </el-slider>
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
        </el-col>
      </el-row>
      <el-row :gutter="20">
        <el-col :span="24"
                :offset="0">
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ThemeDark',
  components: {},
  props: {},
  data () {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }],
      dialogVisible: false,
      activities: [{
        content: '支持使用图标',
        timestamp: '2018-04-12 20:46',
        size: 'large',
        type: 'primary',
        icon: 'el-icon-more'
      }, {
        content: '支持自定义颜色',
        timestamp: '2018-04-03 20:46',
        color: '#0bbd87'
      }, {
        content: '支持自定义尺寸',
        timestamp: '2018-04-03 20:46',
        size: 'large'
      }, {
        content: '默认样式的节点',
        timestamp: '2018-04-03 20:46'
      }],
      switch1: true,
      switch2: true,
      sliderVal: [30, 60],
      marks: {
        0: '0°C',
        8: '8°C',
        37: '37°C',
        50: {
          style: {
            color: '#1989FA'
          },
          label: this.$createElement('strong', '50%')
        }
      }
    }
  },
  computed: {},
  watch: {},
  created () { },
  mounted () { },
  methods: {}
}
</script>

<style lang='less' scoped>
.page {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  background-color: #222933;

  .main {
    width: 100%;
    flex: 1;
    height: 0;
    padding: 15px;
    box-sizing: border-box;
    overflow-y: auto;
  }
}
</style>
