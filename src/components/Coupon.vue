<template>
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
</template>
<script>
export default {
    name: 'app',
    data () {
        return {}
    }
}
</script>

<style>
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
