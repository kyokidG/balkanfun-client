<template>
  <section class="page-module">
    <hero-image imgSrc="http://balkanfun.ro/wp-content/uploads/2018/05/5331272-greece-wallpaper-1.jpg" title="Toate ofertele" height="400"></hero-image>
    <div class="module-content">
      <el-row class="p4">
        <el-col :span="12" :offset="6" class="center">
          <el-radio-group v-model="filter" style="margin-bottom: 30px;">
            <el-radio-button label="offer1">Oferta 1</el-radio-button>
            <el-radio-button label="offer2">Oferta 2</el-radio-button>
          </el-radio-group>
        </el-col>
      </el-row>
      <el-row>
        <el-col :span="20" :offset="2">
          <offers-list :offers="offers" :filter="filter"></offers-list>
        </el-col>
      </el-row>
    </div>
    <balkanfun-footer></balkanfun-footer>
  </section>

</template>

<script>
import RoutesMapConfig from "@router/routes";
import Divider from "../partials/Divider";
import HeroImage from "../partials/HeroImage";
import OffersList from "../partials/OffersList";
import BalkanfunFooter from "../partials/BalkanfunFooter";
import OfferCard from "../components/OfferCard";

import offers from "../../data/offers";

export default {
  name: "OffersPage",
  props: {},
  created: function(){
    this.filter = this.$route.query.filter || null;
  },
  data() {
    return {
      filter: "offer1",
      offers: offers,
    };
  },
  components: {
    Divider,
    HeroImage,
    OffersList,
    OfferCard,
    BalkanfunFooter
  },
};
</script>

<style lang="scss">
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
