<template>
	<div>
  <div id="app" class="styleEditor ">
  	<pre> {{code}}</pre>
  
  </div>
  <div v-html="stylecode">
  	
  </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data(){
  	return{
  		code:``,
  		finalcode:`
			/*
* Inspired by http://strml.net/
* 大家好，我是方方
* 二月了，好多公司都在招聘，你是不是也在准备简历呀。
* 说做就做，我也来写一份简历！
*/
/* 首先给所有元素加上过渡效果 */
* {
  transition: all .3s;
}
/* 白色背景太单调了，我们来点背景 */
html {
  color: rgb(222,222,222); background: rgb(0,43,54);
}
/* 文字离边框太近了 */
.styleEditor {
  padding: .5em;
  border: 1px solid;
  margin: .5em;
  overflow: auto;
  width: 45vw; height: 90vh;
}
/* 代码高亮 */
.token.selector{ color: rgb(133,153,0); }
.token.property{ color: rgb(187,137,0); }
.token.punctuation{ color: yellow; }
.token.function{ color: rgb(42,161,152); }
/* 加点 3D 效果呗 */
html{
  perspective: 1000px;
}
.styleEditor {
  position: fixed; left: 0; top: 0;
  -webkit-transition: none;
  transition: none;
  -webkit-transform: rotateY(10deg) translateZ(-100px) ;
          transform: rotateY(10deg) translateZ(-100px) ;
}
/* 接下来我给自己准备一个编辑器 */
.resumeEditor{
  position: fixed; right: 0; top: 0;
  padding: .5em;  margin: .5em;
  width: 48vw; height: 90vh;
  border: 1px solid;
  background: white; color: #222;
  overflow: auto;
}
/* 好了，我开始写简历了 */
  		`
  		
  	}
  },
  created(){
  	var n=0;
  	setInterval(()=>{
  		this.code=this.finalcode.substring(0,n)
  		
  		n+=1;
  	},10)
  },
//如果是被计算出来的数据放在computed里
computed:{
	stylecode(){
		return '<style>' + this.code + '</style>'
	}
	
}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
  margin-top: 60px;
}
</style>
