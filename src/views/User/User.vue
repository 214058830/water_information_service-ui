<template>
  <div>
    <Row>
      <Col span="6">
        <Menu :active-name="MenuItem" @on-select="selectMenuItem">
          <Menu-group title="用户信息管理">
            <Menu-item name="s1-1">
              <Icon type="document-text"></Icon>录入信息
            </Menu-item>
          </Menu-group>
          <Menu-group title="用户权限管理">
            <Menu-item name="s2-1">
              <Icon type="heart"></Icon>权限管理
            </Menu-item>
          </Menu-group>
        </Menu>
      </Col>
      <Col span="18">
        <div v-show="MenuItem == 's1-1'">
          <AddUser />
        </div>
        <div v-show="MenuItem == 's2-1'">
          <Auth />
        </div>
      </Col>
    </Row>
  </div>
</template>

<script>
import Auth from "./Auth";
import AddUser from "./AddUser";

export default {
  components: {
    Auth,
    AddUser
  },
  data() {
    return {
      MenuItem: "s1-1"
    };
  },
  methods: {
    selectMenuItem(name) {
      this.MenuItem = name;
    }
  },
  mounted() {}
};
</script>

<style scoped>
</style>