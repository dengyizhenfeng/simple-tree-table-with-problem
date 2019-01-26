<template>
  <div id="app">
    <items :model="model" v-for="model in listData" :key="model.orgId"></items>
  </div>
</template>

<script>
import items from "./items.vue";
export default {
  name: "App",
  data() {
    return {
      listData: [
        {
          orgId: 1,
          companyId: 1,
          orgName: "财务部",
          orgType: "	组织类型",
          orgParentId: "父组织ID",
          orgUserNum: "在职人数",
          fullTimeNum: "全职人数",
          orgAs: "人员编制",
          leaderId: "负责人(员工)ID",
          leaderName: "负责人姓名",
          orgShort: "组织简称",
          orgCode: "组织代码",
          orgDesc: "组织描述",
          children: [
            {
              orgId: 2,
              companyId: 2,
              orgName: "财务部",
              orgType: "	组织类型",
              orgParentId: "父组织ID",
              orgUserNum: "在职人数",
              fullTimeNum: "全职人数",
              orgAs: "人员编制",
              leaderId: "负责人(员工)ID",
              leaderName: "负责人姓名",
              orgShort: "组织简称",
              orgCode: "组织代码",
              orgDesc: "组织描述",
              children: [
                {
                  orgId: 4,
                  name: "abcdvdd"
                }
              ]
            }
          ]
        },
        {
          orgId: 3,
          companyId: 3,
          orgName: "财务部",
          orgType: "	组织类型",
          orgParentId: "父组织ID",
          orgUserNum: "在职人数",
          fullTimeNum: "全职人数",
          orgAs: "人员编制",
          leaderId: "负责人(员工)ID",
          leaderName: "负责人姓名",
          orgShort: "组织简称",
          orgCode: "组织代码",
          orgDesc: "组织描述"
        }
      ]
    };
  },
  components: {
    items
  }
};
</script>

<style scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.hide {
  display: none;
}
tr {
  width: 100%;
}
td {
  width: 50px;
}
</style>
