<template>
  <div class="container">
    <div class="tabs">
      <div class="tab-1">
        <a href="">Fresh</a>
      </div>
      <div class="tab-2">
        <a href="">Hot</a>
      </div>
    </div>
  </div>
  <div class="container card-container">
    <div v-for="(item, index) in apiData" :key="index" class="card">
      <div class="card-image">
        <a :href="`https://www.scoopwhoop.com/${item.slug}`">
          <img :src="item.feature_img" alt="" />
        </a>
      </div>
      <div class="card-data">
        <a :href="`https://www.scoopwhoop.com/${item.slug}`">
          <div class="card-subtitle">
            <p>{{ item.category.toString() }}</p>
          </div>
          <div class="card-info">
            <h4>
              {{ item.title }}
            </h4>
          </div>

          <div class="card-author">
            <a
              :href="`https://www.scoopwhoop.com/author/${item.auth_display.author_url}/?ref=read_fresh`"
            >
              {{ item.auth_display.display_name }}
            </a>
          </div>
          <div class="card-date">
            <p>{{ moment(item.pub_date) }}</p>

            <p>{{ item.readtime }}</p>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  props: ["apiData"],
  created() {
    console.log(this.apiData);
  },
  methods: {
    moment: function (date) {
      return moment(date).fromNow();
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 1100px;
  margin: 0 auto;

  margin-top: 20px;
}
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.tabs {
  display: flex;
  border-bottom: 1px solid #1b91ff;
  max-width: 1077px;
  margin: 0 auto;
}
.tab-1,
.tab-2 {
  width: 148px;
  display: block;
  text-align: center;
  padding: 10px 0;
}
.tab-1 a,
.tab-2 a {
  text-decoration: none;
  color: black;
}
.tab-1 {
  background: linear-gradient(158.35deg, #1b91ff 0, #9f49e3 113.59%);
}
.tab-1 a {
  color: white;
}
.card {
  height: 100%;
  flex: 0 0 252px;
  margin: 0 auto 40px;
}
.card-image {
  width: 252px;

  height: 160px;
  margin-bottom: 25px;
}
.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.card-data a {
  text-decoration: none;
  display: block;
  color: #1b91ff;
  font-weight: 300;
}
.card-subtitle p {
  background: linear-gradient(136.04deg, #1b91ff -0.78%, #9f49e3 92.66%)
    no-repeat;
  display: inline-block;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.03em;
  line-height: 19px;
  margin-bottom: 10px;
  margin-top: 0;
  text-decoration: none;
  text-transform: uppercase;
  -webkit-background-clip: text !important;
  -webkit-text-fill-color: transparent;
}

.card-info h4 {
  margin-top: 0;
  color: #1e1e1e;
  display: block;
  font-size: 18px;
  font-weight: 700;
  line-height: 26px;
  margin-bottom: 8px;
  text-decoration: none;
}
.card-info h4:hover {
  color: #1b91ff;
}
.card-author p {
  color: #1b91ff;
  display: block;
  font-size: 12px;
  line-height: 15px;
  margin-bottom: 2px;
  text-decoration: none;
  font-weight: 300;
}
.card-date {
  display: flex;
  max-width: 300px;
  justify-content: space-between;
  color: #898989;
  font-size: 11px;
  line-height: 142.97%;
  font-size: 11px;
}
.card-date p{
    margin: 0;
}

.card:hover .card-image img {
  transform: scale(1.2);
  transition: 0.5s ease;
}

@media screen and (max-width: 600px) {
  .card{
    flex:1 0 90%;
    margin: 0 20px;
  }
  .card-image{
    width: 100%;
  }
}
</style>