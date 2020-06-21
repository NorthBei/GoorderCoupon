<template>
  <div id="app">
    <el-tabs v-model="activeName" id="tab" stretch>
      <el-tab-pane label="我的集點卡" name="first" class="tab-pane">
        <div>
          <div id="profile">
            <div>
              <div>Escer異世客密室逃脫工作室</div>
              <!-- <small>餐廳/咖啡廳</small> -->
            </div>
          </div>
          <img src="./assets/card.jpg" id="loyalty-card">
        </div>
        <el-collapse v-model="collapseActiveNames">
          <el-collapse-item title="使用說明" name="1">
            <div>1. 消費買$600元，即贈送1點</div>
            <div>2. 集滿8點可免費兌換單人免費遊玩體驗券乙張</div>
            <div>3. 活動至2020/06/31截止</div>
          </el-collapse-item>
          <el-collapse-item title="可兌換優惠" name="2" id="coupon-wrapper">
            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="./assets/banner.jpg" class="image">
              <div class="coupon-card-info">
                <div class="title">單人免費遊玩體驗券</div>
                <!-- <div class="subtitle">使用期限：至2020/10/01截止</div> -->
                <div class="bottom">
                  <el-button type="primary" class="button"  @click="dialogVisible = true" disabled>兌換點數</el-button>
                </div>
              </div>
            </el-card>
<!--             
            <div>伊比利生火腿芝麻葉披薩</div>
            <div>夏威夷披薩</div>
            <div>嫩雞蕈菇甜椒披薩</div>
            <div>鮪魚甜玉米披薩</div>
            <div>四種乳酪披薩</div>
            <div>酒釀葡萄蜜蘋果披薩</div>
            <div>大披薩球</div>
            <div>自選雙拼披薩</div> -->
          </el-collapse-item>
        </el-collapse>
      </el-tab-pane>
      <el-tab-pane label="我的優惠券" name="second" class="tab-pane">
        <el-card :body-style="{ padding: '0px' }" class="coupon-card">
          <img src="./assets/banner.jpg" class="image">
          <div class="coupon-card-info">
            <div class="title">6人以上，1人免費體驗</div>
            <div class="subtitle">使用期限：至2020/10/31截止</div>
            <div class="bottom">
              <el-button type="primary" class="button"  @click="isShow = true">兌換優惠</el-button>
            </div>
          </div>
        </el-card>

        <!-- <el-card :body-style="{ padding: '0px' }" class="coupon-card">
          <img src="https://scontent.ftpe12-1.fna.fbcdn.net/v/t1.0-9/67974449_383488462350629_3263426313116975104_o.jpg?_nc_cat=108&_nc_oc=AQm1QcecWBRvcgICrJY_1paOz6C7KWC2cCFCJJT7rOrC03i1d_o8tvDQP0bc5hL1tx4&_nc_ht=scontent.ftpe12-1.fna&oh=e7532b201f74fdca5b2379cdca5a2826&oe=5ECACAEE" class="image">
          <div class="coupon-card-info">
            <div class="title">6人以上，1人免費</div>
            <div class="subtitle">使用期限：至2020/10/01截止</div>
            <div class="bottom">
              <el-button type="primary" class="button"  @click="dialogVisible = true">兌換優惠</el-button>
            </div>
          </div>
        </el-card> -->

      </el-tab-pane>
    </el-tabs>
    <div v-show="isShow" id="dialog">
      <el-button class="arrow" icon="el-icon-back" @click="isShow = false" circle></el-button>
      <img src="./assets/banner.jpg" class="image">
      <div class="content">
        <h2 class="title">6人以上，1人免費體驗</h2>
        <h4>使用期限：至2020年10月31日，剩餘304天</h4>
        <h4>優惠代碼：6PEOPLE-JI3QE9</h4>
        <h4>使用說明：</h4>
        <ul class="list">
          <li>本優惠券適用於異世客任一遊戲。</li>
          <li>本優惠券同時適用於網路預訂與現場折抵，若現場使用請出示優惠券，線上使用請於異世客官網訂購表單內輸入優惠代碼。</li>
          <li>同一團玩家只適用一張優惠券，無法同時使用多張。</li>
        </ul>
      </div>
      <div class="footer">
        <el-button type="primary" class="button"  @click="dialogVisible = true">兌換優惠</el-button>
      </div>
    </div>
    <el-dialog
      :visible.sync="dialogVisible"
      width="30%">
      <span>確定要兌換/使用優惠券嗎？</span>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取消</el-button>
        <el-button type="primary" @click="dialogVisible = false">確定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      isShow: false,
      msg: 'Welcome to Your Vue.js App',
      activeName: 'second',
      collapseActiveNames:['1','2'],
      dialogVisible: false
    }
  }
}
</script>

<style lang="scss">
html,body{
  margin: 0;
  padding: 0;
  width:100%;
  height: 100%;
}
#tab{
  height: 60px;
  width: 100%;
}

#tab .el-tabs__header.is-top{
  margin: 0;
}

#tab .el-tabs__item{
  height: 60px;
  line-height: 60px;
}

#tab .tab-pane{
  margin: 8px;
}

#tab .el-collapse-item__header{
  font-size: 16px;
}

#tab .el-collapse-item__content{
  font-size: 14px;
}
#profile{
  background: #1a1514;
  color: white;
  display: flex;
  align-items: center;
  padding: 8px;
  font-size:18px;
}

#profile img{
  width: 70px;
  margin-right: 8px;
}

#loyalty-card{
  width: 100%;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  font-size: 15px;
}

.el-dialog{
  min-width: 300px;
}

/*coupon card css*/
.coupon-card{
  margin-bottom: 8px;
}

.coupon-card>.el-card__body{
  display: flex;
  flex-direction: column;
  position: relative;
}

.coupon-card img{
  height: 210px;
}

.coupon-card .coupon-card-info{
  flex: 1;
  padding: 12px;
}

.coupon-card .coupon-card-info .title{
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 6px;
}

.coupon-card .right-btn{
  position: absolute;
  right: 17px;
  bottom: 5px;
}

.coupon-card .coupon-card-info .bottom > button{
  margin-top: 12px;
  width: 100%;
}

#dialog {
  position: fixed;
  z-index: 100;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  background: white;
  display: flex;
  flex-direction: column;
}

#dialog .arrow {
  position: absolute;
  top: 20px;
  left: 20px;
  transform: scale(1.2);
}

#dialog .image {
  display: block;
  height: 240px;
}

#dialog .content {
  padding: 12px;
  flex: 1;
  margin-bottom: 75px;
}

#dialog .content .title {
  margin-top: 0;
  margin-bottom: 15px;
}

#dialog .content h4 {
  margin: 15px 0;
}

#dialog .content .list li {
  line-height: 27px;
}

#dialog .footer {
  border-top: 1px solid #e2e0e0;
  padding: 12px;
  position: fixed;
  bottom: 0;
  width: 100%;
  box-sizing: border-box;
  background: white
}

#dialog .footer > button{
  height: 50px;
  width: 100%;
}
</style>
