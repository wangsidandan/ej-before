  <template>
  <el-table :data="categoryList" style="width: 100%">
    <el-table-column prop="id" label="编号" width="180"></el-table-column>
    <el-table-column prop="username" label="昵称"></el-table-column>
    <el-table-column prop="realname" label="姓名"></el-table-column>
    <el-table-column prop="password" label="密码"></el-table-column>
    <el-table-column prop="enabled" label="状态"></el-table-column>
    <el-table-column prop="type" label="类型"></el-table-column>
    <el-table-column prop="telephone" label="电话"></el-table-column>
  </el-table>
</template>
<script>
import request from "@/utils/request";
import qs from "querystring";
export default {
  data() {
    return {
      categoryList:[]
    };
  },
  created() {
    this.loadUsers();
  },
  methods: {
    loadUsers() {
      let url="http://134.175.154.93:6677/customer/findAll"
      request.get(url).then((result)=>{
          this.categoryList=result.data;
      })
    }
  }
}
</script>