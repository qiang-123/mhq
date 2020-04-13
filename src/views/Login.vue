<template>
    <div class="login">
        <h1 class="loginLogo">登录</h1>
        <nut-textinput v-model="account" placeholder='请输入账号' :has-border='false'/>
        <nut-textinput v-model="password" placeholder='请输入密码' type='password' :has-border='false'/>
        <nut-button block @click='login'>登录</nut-button>
        <span class="toRegister" @click='register'>还没账号？</span>
    </div>
</template>
<script>
export default {
    data(){
        return{
            account:'',
            password:''
        }
    },
    methods:{
        login(){
            // 验证账号 昵称格式：限16个字符，支持中英文、数字、减号或下划线
            const regAcc = /^[\\u4e00-\\u9fa5_a-zA-Z0-9-]{6,16}$/
            if(!regAcc.test(this.account)){//验证不通过
                alert('请输入正确的账号')
                return false //中断后续代码执行
            }
            // 验证密码 6-20 位，字母、数字
            const regPsd = /^([A-Z]|[a-z]|[0-9]){6,20}$/
            if(!regPsd.test(this.password)){//验证不通过
                alert('请输入正确的密码')
                return false //中断后续代码执行
            }
            this.$router.push('/')
        },
        register(){
            this.$router.push('/register')
        }
    }
}
</script>
<style lang="scss" scoped>
.login{
    height:100%;
    .loginLogo{
        width:120px;
        height:120px;
        margin:60px auto 25px;
        background: deepskyblue;
    }
    .nut-textinput{
        
        border-bottom:1px solid #000;
    }
}
</style>