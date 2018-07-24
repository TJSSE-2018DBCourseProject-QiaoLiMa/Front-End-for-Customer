<template>
    <div>
      <el-aside class="sidebar" width="420px">
          <div class="form-box">
              <el-form ref="form" :model="form" label-width="80px">
                  <el-form-item label="出发站点">
                      <el-col :span="10">
                        <el-input v-model="form.origin" placeholder = "选择或输入站点"></el-input>
                      </el-col>
                      <el-col :span="2">
                        <el-button type="primary" @click="onSubmit">选择站点</el-button>
                      </el-col>
                  </el-form-item>

                  <el-form-item label="到达站点">
                      <el-col :span="10">
                        <el-input v-model="form.destination" placeholder = "选择或输入站点"></el-input>
                      </el-col>
                      <el-col :span="2">
                        <el-button type="primary" @click="onSubmit">选择站点</el-button>
                      </el-col>
                  </el-form-item>

                  <el-form-item label="出发日期">
                      <el-col :span="11">
                          <el-date-picker type="date" placeholder="选择日期" v-model="form.date" style="width: 100%;"></el-date-picker>
                      </el-col>
                  </el-form-item>

                  <el-form-item label="车次类型">
                      <el-radio-group v-model="form.trainType">
                          <el-radio label="G/高铁"></el-radio>
                          <el-radio label="D/动车"></el-radio>
                          <el-radio label="K/快车"></el-radio>
                      </el-radio-group>
                  </el-form-item>

                  <el-form-item>
                      <el-button type="primary" @click="onSubmit">查询车次</el-button>
                      <el-button >清空表单</el-button>
                  </el-form-item>
              </el-form>
          </div>
      </el-aside>
    </div>
</template>

<style>
  .sidebar{
    background-color: rgb(255,255,255);
    height: "600px";
    overflow-x: hidden;
    border: 1px solid #eee;
  }

  .form-box{
    margin: 10px
  }
</style>

<script>
    export default {
        name: 'baseform',
        data: function(){
            return {
                form: {
                    origin: '',
                    destination: '',
                    date: '',
                    trainType: '',
                    sortBy : 'trainNum'
                }
            }
        },
        methods: {
            onSelectStation(){

            },
            onSubmit() {
                this.$message.success('提交成功！');
                console.log(this.form.trainType);
            }
        }
    }
</script>