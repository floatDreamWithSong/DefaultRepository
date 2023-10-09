<template>
    <div id="nav" >
      <el-row >
        <el-col :span="6" type="flex" align="center">
          <img src="../assets/xiaocheshike.png" alt="" srcset="">
          <div class="iconamediv">{{iconames[0]}}</div>
        </el-col>
        <el-col :span="6" type="flex" align="center">
          <img src="../assets/xiaoli.png" alt="" srcset="">
          <div class="iconamediv">{{iconames[1]}}</div>
        </el-col>
        <el-col :span="6" type="flex" align="center">
          <img src="../assets/xiaoyuanditu.png" alt="" srcset="">
          <div class="iconamediv">{{iconames[2]}}</div>
        </el-col>
        <el-col :span="6" type="flex" align="center">
          <img src="../assets/wodeyouxiang.png" alt="" srcset="">
          <div class="iconamediv">{{iconames[3]}}</div>
        </el-col>
      </el-row>
    </div>
  </template>
  <script>
    export default{
      name:"navTop",
      data() {
        return {
          iconames:["校车时刻","校历","校园地图","我的邮箱"]
        }
      },
    }
  </script>
  <style scoped>
      #nav{
        position: relative;
        z-index: 99;
        padding: 20px 10px;
      }
      img{
        cursor: pointer;
        width:40px;
      }
  </style>