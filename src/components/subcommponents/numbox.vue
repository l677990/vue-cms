<template>
    <div>
        <div class="mui-numbox" data-numbox-min='1'>
			<button class="mui-btn mui-btn-numbox-minus" type="button">-</button>
			<input id="test" class="mui-input-numbox" ref="numbox" @change="countChanged" type="number" value="1" />
			<button class="mui-btn mui-btn-numbox-plus" type="button">+</button>
		</div>
    </div>
</template>

<style lang="stylus" scoped>

</style>

<script>
// 导入MUI的JS文件
import mui from "../../lib/mui/js/mui.min.js"

export default {
    mounted() {
    // 初始化数字选择框组件
    mui(".mui-numbox").numbox();
    console.log(this.max);
  },
  methods: {
    countChanged(){
      // 每当文本框的数据被修改的时候 立即把 最新的数据，通过事件调用输出
        // console.log(this.$refs.numbox.value)
        this.$emit('getcount',parseInt(this.$refs.numbox.value))
    },
  },
    props:["max"],
    watch: {
      //监听属性
      'max':function(newVal,oldVal){
        // mui(".mui-numbox").numbox().setOption("max",newVal)
        mui(".mui-numbox").numbox().setOption('max',newVal)
      }
    },
}
</script>