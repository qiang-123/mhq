<template>
    <div class="seats">
        <div class="seatsTitle">
            {{name}}
            <div class="roomInfo">{{roomInfo}}</div> 
        </div>
        <div class='chooseSeats'>
            <span class="screen">{{`${roomName}荧幕`}}</span>
            <span v-for='n in seats' :key='n' class="iconfont">&#xe69a;</span>
        </div>
        <div class="seatsState">
            <!-- 可选 -->
            <span class="iconfont choosing">&#xe69a;</span>
            <!-- 已选 -->
            <span class="iconfont choosed">&#xe69a;</span>
            <!-- 已售 -->
            <span class="iconfont salled">&#xe69a;</span>
        </div>
        <div class="tickets">
            已选座位
            <div>
                <!-- 座位信息 -->
                <div></div>
                <!-- 价格 -->
                <div></div>
            </div>
        </div>
        <div class="cfmBtn">确认选座</div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            name:'',
            roomInfo:'',
            roomName:'',
            seats:10,
        }
    }
}
</script>
<style lang="scss" scoped>
    .seats{
        .iconfont{
            font-size: 32px;
        }
    }
</style>