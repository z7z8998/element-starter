<template>
  <div id="app">
    <el-container>
      <el-header>
        Header
      </el-header>
      <el-container>
        <el-aside width="250px">Aside</el-aside>
        <el-container>
          <el-main>
            <el-row>
              <el-col
                :span="4"
                v-for="(o, index) in 5"
                :key="o"
                :offset="index > 0 ? 1 : 0"
              >
                <el-card :body-style="{ padding: '0px' }">
                  <img
                    src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"
                    class="image"
                  />
                  <div style="padding: 14px;">
                    <span>好吃的汉堡</span>
                    <div class="bottom clearfix">
                      <time class="time">{{ currentDate }}</time>
                      <el-button @click="startHacking" type="text" class="button">操作按钮</el-button>
                    </div>
                  </div>
                </el-card>
              </el-col>
            </el-row>
          </el-main>
          <el-footer>Footer</el-footer>
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentDate: new Date(),
    };
  },
  methods: {
    startHacking() {
      this.$notify({
        title: "运行正常",
        type: "success",
        message: "当你看到此窗口时，说明 Element-UI 已经可以正常工作了!",
        duration: 5000,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Helvetica, sans-serif;
  text-align: center;
}

.time {
  font-size: 13px;
  color: #999;
}

.bottom {
  margin-top: 13px;
  line-height: 12px;
}

.button {
  padding: 0;
  float: right;
}

.image {
  width: 100%;
  display: block;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both;
}
</style>
