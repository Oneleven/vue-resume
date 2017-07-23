<template>
    <div>
        <h3>工作经历</h3>
        <el-form>
            <div v-for="(work,index) in workHistory">
                <el-form-item label="公司">
                    <el-input v-model="work.company"></el-input>
                </el-form-item>
                <el-form-item label="工作内容">
                    <el-input v-model="work.content"></el-input>
                </el-form-item>
                <i class="el-icon-delete" v-on:click="removeWorkHistory(index)"></i>
                <hr>
            </div>
            <el-button v-on:click="addWorkHistory">添加</el-button>
        </el-form>
    </div>
</template>

<script>
export default {
  props:['workHistory'],
  methods: {
        addWorkHistory() {
            this.workHistory.push({
                company: '', content: ''
            })
        },
        removeWorkHistory(index) {
            this.workHistory.splice(index, 1)
        }
    }
}
</script>

