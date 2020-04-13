<template>
    <div class="register">
        <nut-textinput v-model="account" placeholder='请输入账号' :has-border='false'/>
        <nut-textinput v-model="password" placeholder='请输入密码' type='password' :has-border='false'/>
        <nut-textinput v-model="cfm" placeholder='请确认密码' type='password' :has-border='false'/>
        <input type="checkbox" name="" id="" v-model="check"> 我阅读并已同意协议
        <nut-button block @click='clickhandle'>登录</nut-button>
    </div>
</template>
<script>
export default {
    data(){
        return{
            account:'',
            password:'',
            cfm:'',
            check:false
        }
    },
    methods:{
        clickhandle(){
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
            //确认密码
            if(this.password !== this.cfm){
                alert('两次密码输入不一致')
                return false
            }
             // 验证协议是否勾选
            if(!this.check){
                alert('请先同意协议')
                return false
            }
            this.$router.push('/login')
        }
    }
}
</script>