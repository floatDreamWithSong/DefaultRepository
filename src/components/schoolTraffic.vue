<template>
    <div id="schoolTraffic" type="flex" align="center" >
        <div id="tb">
            <div id="title">{{titlename}}</div>
        </div>
        
        <div id="tra_f_con">
            <el-row type="flex" align="center" justify="space-around">
                <el-col type="flex" align="center">
                    <img :src="tra.back_log.url" class="traimg" alt="">
                    <div class="tramsg">{{tra.back_log.msg}}</div>
                </el-col>
                <el-col type="flex" align="center">
                    <img :src="tra.passage_log.url" class="traimg" alt="">
                    <div class="tramsg">{{tra.passage_log.msg}}</div>
                </el-col>
                <el-col type="flex" align="center">
                    <img :src="tra.stay.url" class="traimg" alt="">
                    <div class="tramsg">{{tra.stay.msg}}</div>
                </el-col>
                <el-col type="flex" align="center">
                    <img :src="tra.goaway.url" class="traimg" alt="">
                    <div class="tramsg">{{tra.goaway.msg}}</div>
                </el-col>
            </el-row>
            <div id="closebox" type="flex" align="center">
                <span @click="changeurl" id="closemsg" >{{close.msg}}</span>
                <img v-show="close.status" @click="changeurl" :src="close.url" id="closeimg">
                <img v-show="!close.status" @click="changeurl" :src="close.url" id="showimg">
            </div>
        </div>

    </div>
</template>
<script>
    export default{
        name:"schoolTraffic",
        data() {
            return {
                titlename:"校园通行",
                tra:{
                    back_log:{
                        msg:"返校登记",
                        url:require("../assets/fanxiaoshenqing.png")
                    },
                    passage_log:{
                        msg:"访客登记",
                        url:require("../assets/qinyoudaishenqing.png")
                    },
                    stay:{
                        msg:"假期留校",
                        url:require("../assets/jiaqiliuxiao.png")
                    },
                    goaway:{
                        msg:"离校离沪",
                        url:require("../assets/lixiaoshenqing.png")
                    }
                },
                close:{
                    status:1,
                    msg:"点击收起",
                    url:require('../assets/bianzu.png'),
                }
            }
        },
        methods:{
            changeurl:function(){
                if (this.close.status) {
                    this.close.status=0;
                    this.showitem = 0;
                    this.close.msg="点击展开";
                } else {
                    this.showitem = 1;
                    this.close.msg="点击收起";
                    this.close.status = 1;
                }
            }
        }
    }
</script>
<style scoped>
    #tb{
        box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.276);
        display: flex;
        justify-content: center;
        background-color: rgb(163, 32, 53);
        width:160px;
        height: 15px;
        transform: translateY(-35px) perspective(20px) rotateX(5deg)
    }
    #title{
        position: absolute;
        transform: translateY(2px) perspective(20px) rotateX(-10deg);
        width: 140px;
        padding: 5px 0;
        text-align: center;
        border-radius: 0 0 10px 10px ;
        background-image: linear-gradient(to bottom,rgb(217, 103, 122),rgb(192, 67, 87));
        color: white;
        font-size: 16px;
        font-weight: 600;
    }
    #tra_f_con{
        padding: 10px 5px;
        border-radius: 10px;
        background-color:white ;
    }
    #schoolTraffic{
        position: relative;
        z-index: 0;
        box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.276);
        padding: 20px 8px 15px 8px;
        position: relative;
        border-radius: 10px;
        margin: 40px 15px 20px 15px;
        background-color:rgb(238, 227, 228);
    }
    .tramsg{
        margin-top: -12px;
        font-size: 14px;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;

    }
    img{
        cursor: pointer;
        width: 70px;
    }
    #closemsg{
        cursor: pointer;
        font-family:'Times New Roman', Times, serif;
        font-weight: 300;
        font-weight: 500;
        color: rgb(183, 87, 102);
    }
    #closeimg{
        width: 12px;
        vertical-align: center;
    }
    #showimg{
        transform: rotate(180deg);
        width: 12px;
        vertical-align: center;
    }
    #closebox{
        font-size: 14px;
        padding: 10px;
    }
</style>