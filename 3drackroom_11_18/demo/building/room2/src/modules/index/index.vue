<style scoped>
  .full-screen {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }

  .bg-purple-dark {
    background: #99a9bf;
  }

  .grid-content {
    border-radius: 4px;
    text-align: center;
    height: 36px;
    line-height: 36px;
  }

  .el-menu--horizontal .el-menu-item {
    float: right !important;
  }

  .el-menu{
    padding-right: 60px;
  }
  .area_pisition{
  	width:100%;
  	height:100%;
  	background-color: #ffffff;
  	z-index:10000;
  	padding:10px;
  }
</style>
<template>
  <div class="full-screen">
      <div class="area_pisition">
      	
<el-form ref="form" :model="form" label-width="80px">

<el-row>
	<el-col :span="6">
		&nbsp
	</el-col>
  <el-col :span="12">
  	<div class="grid-content bg-purple-dark">
  	  <el-form-item label="活动名称">
       <el-input v-model="form.name"></el-input>
      </el-form-item>
    </div>
  </el-col>
  <el-col :span="24">
  	<div class="grid-content bg-purple-dark">
  	  <button @click='get_location'>get_location</button>
    </div>
  </el-col>
</el-row>
 



 
</el-form>
      </div>
  </div>
</template>
<script>
    export default {
      data() {
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
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
        navigator.geolocation.getCurrentPosition(this.showPosition);
      },
      showPosition(position){
	    console.log(position.coords.latitude); 
	    console.log(position.coords.longitude);	
       }
    }
    }
</script>
