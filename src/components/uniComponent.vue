<template>
    <div class="uni">
        <div class="tbox">
            <div class="ttbox">
                <div class="leftline"></div>
                <div class="cbox">
                    <img src="" alt="" class="timg">
                    <span class="tmsg"></span>
                </div>
                <div class="rightline"></div>
            </div>
        </div>
        <div id="use" class="fcon">

        </div>
    </div>
</template>
<script>
export default{
    name:"uniComponent",
    data() {
        return {
            flist:{
                url:[],
                msg:[]
            }
        }
    },
    methods: {
        addf(u,m,idn){
            let el = document.querySelector(idn);
            el.innerHTML+='<div class="fbox"><img src="'+u+'" class="fimg"><div class="fmsg">'+m+'</div></div>';
        },
        getmsg(){
            
        }
    },
}
</script>
<style scoped>
    .uni{
        border-radius: 8px;
        background-color: white;
        margin:8px 16px;
    }
</style>