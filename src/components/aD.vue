<template>
    <el-row id="ad" type="flex" justify="center">
        <div id="adbox" >
            <img :src="adsrc" alt="">
            <i class="btn el-icon-arrow-left"></i>
            <i class="btn el-icon-arrow-right"></i>
        </div>
    </el-row>
</template>
<script>
    export default{
        name:"aD",
        data() {
            return {
                adsrc:require("../assets/s1.png")
            }
        },
    }
</script>
<style scoped>
    #ad{
        z-index: 100;
        transform: translateY(-30px);
    }
    #adbox{
        position: relative;
    }
    .el-icon-arrow-left {
        left: 10%;
        top:40%;
    }
    .el-icon-arrow-left:hover{
        left:15%;
    }

    .el-icon-arrow-right {
        left:83%;
        top:40%;
    }
    .el-icon-arrow-right:hover{
        left: 78%;
    }

    .btn{

        opacity: 0;
        transform: scale(1);
        position: absolute;
        transition: 0.3s;
        z-index: 100;
        padding: 10px;
        background-color: rgba(203, 206, 207, 0.45);
        text-align: center;
        border-radius: 100px;
        color: white;
    }
    .btn:hover{
        opacity: 1;
        cursor: pointer;
        background:  rgba(99, 99, 99, 0.587);
    }
    #adbox>img:hover+i{
        left: 15%;
        opacity: 1;
    }
    #adbox>img:hover+i+i{
        left: 78%;
        opacity: 1;
    }
    img:hover{
        cursor: pointer;
    }
    img{
        box-shadow: -2px -2px 10px rgba(147, 147, 147, 0.498),
        2px 2px 10px rgba(0, 0, 0, 0.416);
        width: 80%;
        margin-left:10% ;
        border-radius: 15px;
    }
</style>