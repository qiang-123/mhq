<template>
    <div id='footer'>
        <nut-row>
            <nut-col :span="8">
                <div class="flex-content" @click="clickHandle(1)">电影</div>
            </nut-col>
            <nut-col :span="8">
                <div class="flex-content" @click="clickHandle(2)">订单</div>
            </nut-col>
            <nut-col :span="8">
                <div class="flex-content" @click="clickHandle(3)">我的</div>
            </nut-col>
        </nut-row>
    </div>
</template>
<script>
export default {
    name:'Footer',
    methods:{
        clickHandle(num){
            if(num === 1) this.$router.push('/')
            if(num === 2) this.$router.push('/order')
            if(num === 3) this.$router.push('/user')

        }
    }
}
</script>
<style lang="scss" scoped>
.flex-content{
    height: 44px;
    line-height: 44px;
    background: rgb(120, 164, 244);
    color:#fff
}
</style>