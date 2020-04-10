<template>
  <div class="home">
      <div class="warpper">
        <div class="homeTitle">影片</div>
        <div class="cardItem" v-for="item in list" :key='item.id'>
          <nut-row>
            <nut-col :span="8">
                <div class="imgWarp">
                  <div class="img"></div>
                </div>
            </nut-col>
            <nut-col :span="16">
                <div class="msg">
                  <div class="movName">{{item.name}}</div>
                  <div class="movMsg">
                    <span>{{item.mov}}</span>
                    <span>{{item.sen}}</span>
                    <span>{{item.rank}}</span>
                  </div>
                  <div class="movTag">{{item.tag.join('、')}}</div>
                  <div class="movAtr">{{item.actor.join(',')}}</div>
                  <nut-button small @click="clickHandle">购票</nut-button>
                </div>
            </nut-col>
        </nut-row>
        </div>
      </div>
      <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Footer from '@/components/Footer.vue'

export default {
  data(){
    return{
      list:[
        {
          id:1,
          name:'芳华',
          rank:'9.9分',
          mov:'2D',
          sen:'IMAX',
          tag:['剧情','爱情','战争'],
          actor:['黄轩','苗苗'] 
        }
      ]
    }
  },
  components: {
    Footer
  },
  methods:{
    clickHandle(){
      this.$router.push('/detail')
    }
  }
}
</script>
<style lang="scss" scoped>
.home{
  height: 100%;
  display: flex;
  flex-direction: column;
  .warpper{
    flex: 1;
    overflow-y: auto;
    .homeTitle{
      height: 44px;
      line-height: 44px;
      background: #fff;
      color: rgb(59, 79, 231);
    }
    .cardItem{
      background: lightgray;
      .imgWarp,.msg{
        height: 180px;
        width: 100%;
        box-sizing: border-box;
        padding:3px;
      }  
      .img{
        width: 100%;
        height: 100%;
        background: red;
      }
      .movName,.movMsg,.movTag,.movAtr{
        text-align: left;
      }
    }
  }
}
</style>