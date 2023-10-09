<template>
    <div id="schoolCard">
        <el-container >
            <div>
                <div id="title" align="center" type="flex" justify="center" >
                    <div id="titlecon" align="center" type="flex">
                        <img :src="title_msg.url" alt="qianbao">
                        <span id="titlename">{{title_msg.msg}}</span>
                    </div>
                </div>
            </div>
            <el-main>
                <el-row type="flex" justify="space-around">
                    <el-col :span="8" type="flex" align="center" style="border-right:1px solid rgba(233, 231, 231)">
                        <div class="accountData">{{user_msg.accountRemain.data}} <span class="wei">元</span> </div>
                        <div class="actDataName">{{user_msg.accountRemain.msg}}</div>
                    </el-col>
                    <el-col :span="8" type="flex" align="center" style="border-right:1px solid rgba(233, 231, 231)">
                        <div class="accountData">{{user_msg.consumption.data}} <span class="wei">元</span> </div>
                        <div class="actDataName">{{user_msg.consumption.msg}}</div>
                    </el-col>
                    <el-col :span="8" type="flex" align="center">
                        <div class="accountData">{{user_msg.recharge.data}} <span class="wei">元</span> </div>
                        <div class="actDataName">{{user_msg.recharge.msg}}</div>
                    </el-col>
                </el-row>
                <el-row v-show="showitem" id="itemscon" type="flex" justify="space-around">
                    <div class="items" type="flex" align="center">
                        <img :src="item_msg.ecard.url" alt="">
                        <div class="itemmsg">
                                {{item_msg.ecard.msg}}
                        </div>
                    </div>
                    <div class="items" type="flex" align="center">
                        <img :src="item_msg.reward.url" alt="">
                        <div class="itemmsg">
                            {{item_msg.reward.msg}}
                        </div>
                    </div>
                    <div class="items"  type="flex" align="center">
                        <img :src="item_msg.education_pay.url" alt="">
                        <div class="itemmsg">
                            {{item_msg.education_pay.msg}}
                        </div>
                    </div>
                    <div class="items" type="flex" align="center">
                        <img :src="item_msg.books_pay.url" alt="">
                        <div class="itemmsg">
                            {{item_msg.books_pay.msg}}
                        </div>
                    </div>
                </el-row>
                <el-row id="excon" type="flex" justify="start">
                    <div :span="8" class="extra_f">
                        <img class="eximg" :src="extra_function.get_ecard.url" alt="">
                        <span class="exmsg">{{extra_function.get_ecard.msg}}</span>
                    </div>
                    <div :span="8" class="extra_f">
                        <img class="eximg" :src="extra_function.change_cardnum.url" alt="">
                        <span class="exmsg">{{extra_function.change_cardnum.msg}}</span>
                    </div>
                </el-row>
            </el-main>
            <el-footer height >
                <el-row type="flex" justify="center">
                    <el-col :span="8" type="flex" align="center" justify="space-around">
                        <span @click="changeurl" id="closemsg" >{{close.msg}}</span>
                        <img v-show="close.status" @click="changeurl" :src="close.url" id="closeimg">
                        <img v-show="!close.status" @click="changeurl" :src="close.url" id="showimg">
                    </el-col>
                </el-row>
            </el-footer>
          </el-container>
    </div>
</template>
<script>
    export default{
        name:"schoolCard",
        data() {
            return {
                showitem:1,
                title_msg:{
                    msg:"校园卡钱包",
                    url:require("../assets/xiaoyuankaqianbao.png")
                },
                user_msg:{
                    accountRemain:{msg:"账户余额",data:199999987.70},
                    consumption:{msg:"本月消费",data:9999999123.75},
                    recharge:{msg:"本月充值",data:9999999200.00}
                },
                item_msg:{
                    ecard:{
                        msg:"Ecard小程序",
                        url:require("../assets/xiaoyuankachongzhi.png")
                    },
                    reward:{
                        msg:"奖励补贴",
                        url:require("../assets/shouruchaxun.png")
                    },
                    education_pay:{
                        msg:"教育缴费",
                        url:require("../assets/jiaoyujiaofei.png")
                    },
                    books_pay:{
                        msg:"教材费",
                        url:require("../assets/jiaocaifei.png")
                    }
                },
                extra_function:{
                    get_ecard:{
                        msg:"领取电子卡",
                        url:require("../assets/lingqudianzika.png")
                    },
                    change_cardnum:{
                        msg:"电子卡换号",
                        url:require("../assets/dianzikahuanhao2.png")
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
            inquireUsermsg(){
                alert(2)
            },
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
    *{
        font-size:14px;
        font-family:'Times New Roman', Times, serif;
        font-weight: 300;
    }
    #schoolCard{
        position: relative;
        z-index: 99;
        box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.153);
        border-radius: 10px;
        padding:20px 10px;
        margin:0px 20px;
        background-color: rgb(255, 255, 255);
    }
    #showimg{
        transform: rotate(180deg);
    }
    .accountData{
        cursor: pointer;
        font-size: 22px;
        font-family:'Times New Roman', Times, serif;
        color: rgb(163, 32, 53);
    }
    span[class='wei']{
        margin-left:-5px;
        font-size:12px;
    }
    #titlename{
        font-family:sans-serif;
        font-weight: 350;
        font-size: 18px;
        margin-left: 10px;
        padding: auto;
        text-align: center;
       
    }
    img[alt='qianbao']{
        vertical-align: top;
        height: 25px;
    }
    #itemscon{
        padding:20px 0 0 0 ;
        margin-top: 20px;
    }
    .items>img{
        cursor: pointer;
        width:38px;
    }
    #excon{
        border-top: 1px solid rgb(233, 231, 231);
        padding-top: 15px;
        margin-top: 15px;
    }
    #excon>div{
        cursor: pointer;
        margin-right: 10px;
        padding: 8px;
        border-radius: 4px;
        box-shadow: 1px 1px 2px  rgba(229, 229, 229),
        -1px -1px 2px rgb(229, 229, 229);
    }
    .eximg{
        vertical-align: bottom;
        width: 18px;
    }
    .exmsg{
        font-size: 14px;
        padding: 2px 0;
        text-align: center;
        margin-left: 5px;
    }
    #closemsg{
        cursor: pointer;
        font-weight: 500;
        color: rgb(183, 87, 102);
    }
    #closeimg{
        width: 12px;
        vertical-align: center;
    }
    #showimg{
        width: 12px;
        vertical-align: center;
    }
</style>