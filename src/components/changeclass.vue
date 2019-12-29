<template>
    <div class="change">
        <h1>{{ temp }}</h1>
        <ul>
          <NewComponent :arr="arr"/>
        </ul>
        <div>
            <ul>
                <li>
                学生手机号：<input type="text" v-model="studentmobile">
                </li>
                <li>
                老师email：<input type="text" v-model="teacheremail">
                </li>
                <li>
                课包：<select v-model="courseId">                        //select下拉框
                                <option value="186" selected>186</option>
                                <option value="187" >187</option>
                                </select>
                </li>
            </ul>
         </div>
     <input type="button" value="换班" v-on:click="ChangeStu">
</div>

</template>

<script>
export default {
  name: '快速换班',
  data () {
    return {
      temp:'',
      arr: [], // methods内的函数需要的变量需要现在data中定义，避免函数内是window对象。
      studentmobile: '15900000001',
      courseId: '186',
      teacheremail: 'lixinwei'
    }
  },
  mounted: function () { // mounted函数指的页面一渲染首先执行的函数。 这里首先执行showlist函数
    this.showList()
  },
  methods: {
    // 函数一般都写在这里，可以写多个函数。
    showList: function () { // 这里是写死一个数组，data里的空列表实际就是为了这个数组而声明一下，不然this指的是window对象，而不是data中的列表。
      this.arr = [{
        studentmobile: '15900000001', teacheremail: 'lixinwei@vipkid.com.cn', courseId: 186}]
    },
    ChangeStu () { // 绑定事件的函数，在arr数组中添加用户在input框中输入的内容。提交之后就能实时渲染到页面了。
      this.arr.push({mobile: this.studentmobile, email: this.teacheremail, courseId: this.courseId})
    }}
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
    /*display: inline-block;*/
    margin: 0 10px;
    margin-bottom: 10px;
}
a {
    color: #42b983;
}
</style>
