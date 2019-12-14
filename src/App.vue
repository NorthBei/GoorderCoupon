<template>
  <div id="app">
    <el-tabs v-model="activeName" id="tab" stretch>
      <el-tab-pane label="我的集點卡" name="first" class="tab-pane">
        <div>
          <div id="profile">
            <div>
              <div>斯比亞咖琲披薩</div>
              <small>餐廳/咖啡廳</small>
            </div>
          </div>
          <img src="./assets/card.jpg" id="loyalty-card">
        </div>
        <el-collapse v-model="collapseActiveNames">
          <el-collapse-item title="使用說明" name="1">
            <div>1.消費$500贈送1點</div>
            <div>2.集滿8點可免費兌換任一口味大披薩一個！</div>
            <div>3.活動至2019.01.01截止</div>
          </el-collapse-item>
          <el-collapse-item title="可兌換優惠" name="2" id="coupon-wrapper">
            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
              <div class="coupon-card-info">
                <div>經典A.O.P披薩</div>
                <div>Aglio. Olio and Pepperoncino Pizza</div>
                <div class="bottom right-btn">
                  <el-button type="text" class="button"  @click="dialogVisible = true">兌換</el-button>
                </div>
              </div>
            </el-card>

            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
              <div class="coupon-card-info">
                <div>臘腸蕈菇披薩</div>
                <div>Salaim and Mushroom Pizza</div>
                <div class="bottom right-btn">
                  <el-button type="text" class="button"  @click="dialogVisible = true">兌換</el-button>
                </div>
              </div>
            </el-card>

            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
              <div class="coupon-card-info">
                <div>瑪格麗特披薩</div>
                <div>Margarita Pizza</div>
                <div class="bottom right-btn">
                  <el-button type="text" class="button"  @click="dialogVisible = true">兌換</el-button>
                </div>
              </div>
            </el-card>
            
            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
              <div class="coupon-card-info">
                <div>煙燻鮭魚酸豆披薩</div>
                <div>Smoked Salmon Pizza</div>
                <div class="bottom right-btn">
                  <el-button type="text" class="button"  @click="dialogVisible = true">兌換</el-button>
                </div>
              </div>
            </el-card>

            <el-card :body-style="{ padding: '0px' }" class="coupon-card">
              <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
              <div class="coupon-card-info">
                <div>漁夫海鮮披薩</div>
                <div>Shrimp Scallop and Squid Pizza</div>

                <div class="bottom right-btn">
                  <el-button type="text" class="button"  @click="dialogVisible = true">兌換</el-button>
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
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
          <div class="coupon-card-info">
            <div>經典A.O.P披薩</div>
            <div>Aglio. Olio and Pepperoncino Pizza</div>
            <div class="bottom right-btn">
              <el-button type="text" class="button"  @click="dialogVisible = true">使用</el-button>
            </div>
          </div>
        </el-card>

        <el-card :body-style="{ padding: '0px' }" class="coupon-card">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaVc_51CwSCLrDgfOERVERN5pkbGj7gosh3yzbJQ7WFk23O738vQ" class="image">
          <div class="coupon-card-info">
            <div>臘腸蕈菇披薩</div>
            <div>Salaim and Mushroom Pizza</div>
            <div class="bottom right-btn">
              <el-button type="text" class="button"  @click="dialogVisible = true">使用</el-button>
            </div>
          </div>
        </el-card>

      </el-tab-pane>
    </el-tabs>
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
      msg: 'Welcome to Your Vue.js App',
      activeName: 'first',
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
  position: relative;
}

.coupon-card img{
  height: 120px;
}

.coupon-card .coupon-card-info{
  flex: 1;
  padding: 12px;
}

.coupon-card .right-btn{
  position: absolute;
  right: 17px;
  bottom: 5px;
}
</style>
