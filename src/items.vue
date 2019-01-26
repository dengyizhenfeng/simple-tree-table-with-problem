<template>
  <!-- <li>
        <div @click='toggle'>
            <i v-if='isFolder' class="fa " :class="[open?'fa-folder-open':'fa-folder']"></i>
            <i v-if='!isFolder' class="fa fa-file-text"></i> {{model.data.menuName}}
        </div>
        <ul v-show="open" v-if='isFolder'>
            <items v-for='(cel,i) in model.childTreeNode' :key="1" :model='cel'></items>
        </ul>
  </li>-->
  <div>
    <tr @click="zhankai">
      <td
        v-for="(value, key) in model"
        :key="key"
        :class="key === 'children' ? 'hide' : 'show'"
      >{{ value }}</td>
    </tr>
    <tr v-if="isFolder" v-show="open">
      <items
        v-for="(item, i) in model.children"
        :key="item.orgId"
        :model="item"
        :class="key === 'children' ? 'hide' : 'show'"
      ></items>
    </tr>
  </div>
</template>
<script type="text/javascript">
export default {
  name: "items",
  props: ["model"],
  components: {},
  data() {
    return {
      open: false
    };
  },
    computed: {
      isFolder: function() {
        return this.model.children && this.model.children.length;
      }
    },
    methods: {
      zhankai: function() {
        if (this.isFolder) {
          this.open = !this.open;
        }
      }
    }
};
</script>
<style lang="less" scoped>
.hide {
  display: none;
}
tr{
    width: 100%;
}
/deep/td{
    width: 50px;
}
/deep/.show{
    width: 50px !important;
}
</style>