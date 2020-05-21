<template>
  <div class="hello">
    <input type="text" readonly="readonly" placeholder="请选择分期产品" @click="clickKindList" v-model="params.kindName">
    <nut-picker
        :is-visible="kindListState"
        :default-value-data="kindListDefault"
        :list-data="kindListArr"
        @close="switchPicker('kindListState')"
        @confirm="setkindList">
    </nut-picker>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      kindListArr:[["兴业消金", "马上消金", "度小满", "健信赊销", "民生银行", "健信贴息", "健信分期", "海尔消金"]],
      kindListState:false,
      kindListDefault:[],
      params:{
        kindName:''
      }
    }
  },
  methods:{
    switchPicker(obj){//打开关闭picker
      this[obj] = !this[obj]
    },
    setkindList(chooseData){//分期产品确认
      console.log(chooseData)
    },
    clickKindList(){//分期产品下拉框
      this.kindListState = true;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
