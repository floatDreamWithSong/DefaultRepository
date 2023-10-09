<template>
    <div id="userBox" >
        <div id="usercontainer">
            <img :src="user.userimg" alt="">
            <div id="appname">{{appname}}</div>
            <h2>欢迎你，{{user.username}}</h2>
        </div>
    </div>
  </template>
  <script>
    export default{
      name:"userBox",
      data() {
        return {
            appname:"ECNU随师办",
            user:{
                userimg:require("../assets/0.jpg"),
                username:"邓涵杰"
        }
        }
      }
    }
  </script>
  <style scoped>
    #userBox{
      position: relative;
      z-index: 99;
      height: 150px;
      background: rgb(184, 55, 77);
    }
    img{
      cursor: pointer;
      border: 2px solid rgb(178, 61, 61);
      box-shadow:  2px 2px 10px rgba(0, 0, 0, 0.534) ;
        margin-left: 20px;
        margin-top: 25px;
        width:65px;
        border-radius: 500px;
    }
    h2{
        position: absolute;
        margin-top: -40px;
        left:100px;
        color: white;
        font-weight: 500;
    }
    #appname{
       color: white;
        position: absolute;
        left: 100px;
        margin-top: -65px;
    }
  </style>