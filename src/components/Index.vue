<template>
  <div id="swipe">
    <mt-swipe :auto="4000">
      <mt-swipe-item class="slide1">1</mt-swipe-item>
      <mt-swipe-item class="slide2">2</mt-swipe-item>
      <mt-swipe-item class="slide3">3</mt-swipe-item>
    </mt-swipe>
    <mt-field label="维修业主" placeholder="请输入维修业主" v-model="username"></mt-field>
    <mt-field label="联系方式" placeholder="请输入联系方式" type="tel" v-model="phone"></mt-field>
    <!--<mt-field label="维修时间" placeholder="请输入维修时间" type="time" v-model="time"></mt-field>-->
    <mt-cell class="mint-cell mint-field" title="维修时间">
      <el-time-select v-model="time" :picker-options="{start: '08:30',step: '00:15', end: '18:30'}"
                      placeholder="维修时间"></el-time-select>
    </mt-cell>
    <mt-cell class="mint-cell mint-field" title="维修类型">
      <el-cascader :options="options" change-on-select></el-cascader>
    </mt-cell>
    <mt-cell class="mint-cell mint-field" title="维修地点">
      <el-cascader :options="options2" change-on-select></el-cascader>
    </mt-cell>
    <mt-button @click.native="handleClick" type="primary" class="sumbit_save" size="large">提交</mt-button>
  </div>

</template>
<script>
  export default {
    name: 'index',
    data(){
      return {
        username: '',
        phone: '',
        number: '',
        time: '',
        selected: 'axure',
        options: [{
          value: '物业维修',
          label: '维修',
          children: [{
            value: 'shuidian',
            label: '水电维修'
          }, {
            value: 'jijian',
            label: '基建维修'
          }, {
            value: 'diban',
            label: '地板维修'
          }, {
            value: 'nuanqi',
            label: '暖气维修'
          }]
        }],
        options2: [{
          value: 'A区',
          label: 'A区',
          children: [{
            value: '大车修理区',
            label: '大车修理区',
            children: [{
              value: '1-1',
              label: '1-1'
            }, {
              value: '1-2',
              label: '1-2'
            }, {
              value: '1-3',
              label: '1-3'
            }, {
              value: '1-4',
              label: '1-4'
            }, {
              value: 'button',
              label: 'Button 按钮'
            }]
          }, {
            value: '小车修理区',
            label: '小车修理区',
            children: [{
              value: 'radio',
              label: 'Radio 单选框'
            }, {
              value: 'checkbox',
              label: 'Checkbox 多选框'
            }, {
              value: 'input',
              label: 'Input 输入框'
            }, {
              value: 'input-number',
              label: 'InputNumber 计数器'
            }, {
              value: 'select',
              label: 'Select 选择器'
            }, {
              value: 'cascader',
              label: 'Cascader 级联选择器'
            }, {
              value: 'switch',
              label: 'Switch 开关'
            }, {
              value: 'slider',
              label: 'Slider 滑块'
            }, {
              value: 'time-picker',
              label: 'TimePicker 时间选择器'
            }, {
              value: 'date-picker',
              label: 'DatePicker 日期选择器'
            }, {
              value: 'datetime-picker',
              label: 'DateTimePicker 日期时间选择器'
            }, {
              value: 'upload',
              label: 'Upload 上传'
            }, {
              value: 'rate',
              label: 'Rate 评分'
            }, {
              value: 'form',
              label: 'Form 表单'
            }]
          }, {
            value: '仓储服务区',
            label: '仓储服务区',
            children: [{
              value: 'table',
              label: 'Table 表格'
            }, {
              value: 'tag',
              label: 'Tag 标签'
            }, {
              value: 'progress',
              label: 'Progress 进度条'
            }, {
              value: 'tree',
              label: 'Tree 树形控件'
            }, {
              value: 'pagination',
              label: 'Pagination 分页'
            }, {
              value: 'badge',
              label: 'Badge 标记'
            }]
          }, {
            value: '驾驶员生活公寓',
            label: '驾驶员生活公寓',
            children: [{
              value: 'alert',
              label: 'Alert 警告'
            }, {
              value: 'loading',
              label: 'Loading 加载'
            }, {
              value: 'message',
              label: 'Message 消息提示'
            }, {
              value: 'message-box',
              label: 'MessageBox 弹框'
            }, {
              value: 'notification',
              label: 'Notification 通知'
            }]
          }, {
            value: 'others',
            label: 'Others',
            children: [{
              value: 'dialog',
              label: 'Dialog 对话框'
            }, {
              value: 'tooltip',
              label: 'Tooltip 文字提示'
            }, {
              value: 'popover',
              label: 'Popover 弹出框'
            }, {
              value: 'card',
              label: 'Card 卡片'
            }, {
              value: 'carousel',
              label: 'Carousel 走马灯'
            }, {
              value: 'collapse',
              label: 'Collapse 折叠面板'
            }]
          }]
        }, {
          value: 'B区',
          label: 'B区',
          children: [{
            value: '大车修理区',
            label: '大车修理区',
            children: [{
              value: '1-1',
              label: '1-1'
            }, {
              value: '1-2',
              label: '1-2'
            }, {
              value: '1-3',
              label: '1-3'
            }, {
              value: '1-4',
              label: '1-4'
            }, {
              value: '1-5',
              label: '1-5'
            }, {
              value: '1-6',
              label: '1-6'
            }, {
              value: '1-7',
              label: '1-7'
            }]
          }, {
            value: '小车修理区',
            label: '小车修理区',
            children: [{
              value: '1-1',
              label: '1-1'
            }, {
              value: '1-2',
              label: '1-2'
            }, {
              value: '1-3',
              label: '1-3'
            }, {
              value: '1-4',
              label: '1-4'
            }, {
              value: '1-5',
              label: '1-5'
            }, {
              value: '1-6',
              label: '1-6'
            }, {
              value: '1-7',
              label: '1-7'
            }]
          }, {
            value: '仓储服务区',
            label: '仓储服务区',
            children: [{
              value: 'table',
              label: 'Table 表格'
            }, {
              value: 'tag',
              label: 'Tag 标签'
            }, {
              value: 'progress',
              label: 'Progress 进度条'
            }, {
              value: 'tree',
              label: 'Tree 树形控件'
            }, {
              value: 'pagination',
              label: 'Pagination 分页'
            }, {
              value: 'badge',
              label: 'Badge 标记'
            }]
          }, {
            value: '驾驶员生活公寓',
            label: '驾驶员生活公寓',
            children: [{
              value: 'alert',
              label: 'Alert 警告'
            }, {
              value: 'loading',
              label: 'Loading 加载'
            }, {
              value: 'message',
              label: 'Message 消息提示'
            }, {
              value: 'message-box',
              label: 'MessageBox 弹框'
            }, {
              value: 'notification',
              label: 'Notification 通知'
            }]
          }, {
            value: 'navigation',
            label: 'Navigation',
            children: [{
              value: 'menu',
              label: 'NavMenu 导航菜单'
            }, {
              value: 'tabs',
              label: 'Tabs 标签页'
            }, {
              value: 'breadcrumb',
              label: 'Breadcrumb 面包屑'
            }, {
              value: 'dropdown',
              label: 'Dropdown 下拉菜单'
            }, {
              value: 'steps',
              label: 'Steps 步骤条'
            }]
          }, {
            value: 'others',
            label: 'Others',
            children: [{
              value: 'dialog',
              label: 'Dialog 对话框'
            }, {
              value: 'tooltip',
              label: 'Tooltip 文字提示'
            }, {
              value: 'popover',
              label: 'Popover 弹出框'
            }, {
              value: 'card',
              label: 'Card 卡片'
            }, {
              value: 'carousel',
              label: 'Carousel 走马灯'
            }, {
              value: 'collapse',
              label: 'Collapse 折叠面板'
            }]
          }]
        }]
      }
    },
    methods: {
      handleClick(){
        console.log('submit!');
      }
    }

  };
</script>
<style>
  .mint-swipe {
    height: 200px;
    color: #fff;
    font-size: 30px;
    text-align: center;
    margin-bottom: 20px;
  }

  .sumbit_save {
    right: 0;
    bottom: 8%;
    left: 0;
    position: fixed;
    z-index: 1;
  }

  .mint-swipe-item {
    line-height: 200px;
  }

  .slide1 {
    background-color: #0089dc;
    color: #fff;
  }

  .slide2 {
    background-color: #ffd705;
    color: #000;
  }

  .slide3 {
    background-color: #ff2d4b;
    color: #fff;
  }
</style>
