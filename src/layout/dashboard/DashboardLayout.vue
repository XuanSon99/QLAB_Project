<template>
  <div class="wrapper">
    <side-bar>
      <template slot="links">
        <sidebar-link to="/bang-dieu-khien"
          ><i class="fa fa-home"></i>Bảng điều khiển</sidebar-link
        >
        <sidebar-link to="/danh-sach-thanh-vien"
          ><i class="fa fa-briefcase"></i>Danh sách thành viên</sidebar-link
        >
        <sidebar-link to="/vat-tu"
          ><i class="fas fa-layer-group"></i>Vật tư</sidebar-link
        >
        <v-list-group :value="true">
          <template v-slot:activator>
            <sidebar-link to="/kho-may"
              ><i class="fa fa-home"></i>Kho / máy</sidebar-link
            >
          </template>
          <v-list-item link>
            <sidebar-link to="/may"
              ><i class="fas fa-plus" style="margin-left: 20px"></i>
              Máy</sidebar-link
            >
          </v-list-item>
        </v-list-group>

        <sidebar-link to="/don-vi"
          ><i class="fas fa-gem"></i>Đơn vị</sidebar-link
        >
        <sidebar-link to="/noi-kiem"
          ><i class="fas fa-check-square"></i>Nội kiểm</sidebar-link
        >
        <sidebar-link to="/dinh-muc"
          ><i class="fas fa-gem"></i>Định mức xét nghiệm</sidebar-link
        >
        <!-- <sidebar-link to="/nha-cung-cap"
          ><i class="fas fa-building"></i>Nhà cung cấp</sidebar-link
        > -->
        <sidebar-link to="/yeu-cau-xet-nghiem"
          ><i class="fas fa-user-check"></i>Yêu cầu xét nghiệm</sidebar-link
        >
        <sidebar-link to="/ton-kho"
          ><i class="fas fa-warehouse"></i>Tồn kho</sidebar-link
        >
        <sidebar-link to="/phieu-linh"
          ><i class="fas fa-clipboard"></i>Phiếu Lĩnh HIS</sidebar-link
        >
        <sidebar-link to="/hoa-chat-sap-het"
          ><i class="fas fa-dumpster-fire"></i>Hóa chất sắp hết</sidebar-link
        >
        <sidebar-link to="/muon-hoa-chat"
          ><i class="fas fa-dumpster-fire"></i>Mượn hóa chất</sidebar-link
        >
        <!-- <sidebar-link to="/hoa-chat-nhap-kho"
          ><i class="fas fa-sign-in-alt"></i>Hóa chất nhập kho</sidebar-link
        > -->
        <!-- <sidebar-link to="/hoa-chat-xuat-kho"
          ><i class="fas fa-external-link-alt"></i>Hóa chất xuất
          kho</sidebar-link
        >
        <sidebar-link to="/hoa-chat-het-han"
          ><i class="fas fa-exclamation-triangle"></i>Hóa chất hết
          hạn</sidebar-link
        >
        <sidebar-link to="/vat-tu-hoa-chat"
          ><i class="fas fa-bong"></i>Vật tư, hóa chất</sidebar-link
        >
        <sidebar-link to="/thong-ke-ton-kho"
          ><i class="fas fa-trash-alt"></i>Thống kê tồn kho</sidebar-link
        > -->
      </template>
      <mobile-menu>
        <!-- <li class="nav-item">
          <router-link tag="a" class="nav-link" to="">
            <i class="ti-settings"></i>Tính năng
          </router-link>
        </li>
        <li class="nav-item">
          <router-link tag="a" class="nav-link" to="">
            <i class="ti-settings"></i>Giới thiệu
          </router-link>
        </li>
        <li class="nav-item">
          <router-link tag="a" class="nav-link" to="">
            <i class="ti-settings"></i>Liên hệ
          </router-link>
        </li> -->
        <drop-down
          class="nav-item"
          title="Cài đặt"
          title-classes="nav-link"
          icon="ti-settings"
        >
          <router-link
            tag="a"
            class="dropdown-item"
            to="/thong-tin-ca-nhan"
            @click.native="toggleSidebar"
            >Thông tin cá nhân</router-link
          >
          <a class="dropdown-item">Đăng xuất</a>
        </drop-down>
        <li class="divider"></li>
      </mobile-menu>
    </side-bar>
    <div class="main-panel">
      <top-navbar></top-navbar>

      <dashboard-content @click.native="toggleSidebar"> </dashboard-content>

      <content-footer></content-footer>
    </div>
  </div>
</template>
<style lang="scss">
.wrapper .sidebar .nav i {
  font-size: 14px !important;
  line-height: 20px !important;
}
.v-list-item {
  padding: 0 !important;
}
.v-list-item--link:before {
  background: none !important;
}
</style>
<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./Content.vue";
import MobileMenu from "./MobileMenu";
export default {
  components: {
    TopNavbar,
    ContentFooter,
    DashboardContent,
    MobileMenu,
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    },
  },
};
</script>
