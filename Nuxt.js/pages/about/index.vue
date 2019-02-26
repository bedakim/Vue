<template>
  <div id="pro">
    <div>
      <input type="text" v-model="search" placeholder="뭐찾으려고?">
      <label>search:{{search}}</label>
    </div>
    <section v-for="pro in computed.filterList" :key="pro.id" class="about">
      <ul>
        <li>{{pro.name}}</li>
      </ul>
      <h1>{{pro.name}}</h1>
      <div>
        <img :src="pro.thumb_url" :alt="pro.name">
      </div>
      <p>{{pro.base_price}}</p>
    </section>
  </div>
</template>



<script>
export default {
  data() {
    return {
      el: "#pro",
      // current_page: 2,
      // data: {
      search: "",
      pros: [
        {
          id: 50795,
          mall_id: 13,
          product_code: "200312",
          name: "해피롱티셔츠",
          brand: "",
          base_price: 19800,
          sale_price: 17820,
          thumb_url:
            "http://cdn2-aka.makeshop.co.kr/shopimages/jjh9831/0520070113123.jpg?1543472453",
          big_image_url:
            "http://lylon.co.kr/shopimages/jjh9831/0520070113122.jpg?1543472453",
          detail_url:
            "http://www.lylon.co.kr/shop/shopdetail.html?branduid=200312",
          is_sold_out: 0,
          created_at: "2019-01-08 01:41:43",
          deleted_at: null
        },
        {
          id: 50796,
          mall_id: 13,
          product_code: "200308",
          name: "시크롱티셔츠",
          brand: "",
          base_price: 14000,
          sale_price: 12600,
          thumb_url:
            "http://cdn2-aka.makeshop.co.kr/shopimages/jjh9831/0520070113083.jpg?1543396331",
          big_image_url:
            "http://lylon.co.kr/shopimages/jjh9831/0520070113082.jpg?1543396331",
          detail_url:
            "http://www.lylon.co.kr/shop/shopdetail.html?branduid=200308",
          is_sold_out: 0,
          created_at: "2019-01-08 01:41:47",
          deleted_at: null
        },
        {
          id: 50797,
          mall_id: 13,
          product_code: "200290",
          name: "기모빅성조기롱티",
          brand: "",
          base_price: 26000,
          sale_price: 23400,
          thumb_url:
            "http://cdn2-aka.makeshop.co.kr/shopimages/jjh9831/0520070113023.gif?1543380338",
          big_image_url:
            "http://lylon.co.kr/shopimages/jjh9831/0520070113022.jpg?1543380338",
          detail_url:
            "http://www.lylon.co.kr/shop/shopdetail.html?branduid=200290",
          is_sold_out: 0,
          created_at: "2019-01-08 01:41:50",
          deleted_at: null
        },
        {
          id: 50880,
          mall_id: 13,
          product_code: "200287",
          name: "무비폴라니트",
          brand: "",
          base_price: 22000,
          sale_price: 19800,
          thumb_url:
            "http://cdn2-aka.makeshop.co.kr/shopimages/jjh9831/0520070113013.jpg?1543375414",
          big_image_url:
            "http://lylon.co.kr/shopimages/jjh9831/0520070113012.jpg?1543375414",
          detail_url:
            "http://www.lylon.co.kr/shop/shopdetail.html?branduid=200287",
          is_sold_out: 0,
          created_at: "2019-01-08 01:50:18",
          deleted_at: null
        },
        {
          id: 50798,
          mall_id: 13,
          product_code: "200279",
          name: " MAIN기모티셔츠",
          brand: "",
          base_price: 19800,
          sale_price: 17820,
          thumb_url:
            "http://cdn2-aka.makeshop.co.kr/shopimages/jjh9831/0520070112993.jpg?1543303437",
          big_image_url:
            "http://lylon.co.kr/shopimages/jjh9831/0520070112992.jpg?1543303437",
          detail_url:
            "http://www.lylon.co.kr/shop/shopdetail.html?branduid=200279",
          is_sold_out: 0,
          created_at: "2019-01-08 01:41:54",
          deleted_at: null
        }
      ],
      // },
      computed: {
        filterList() {
          arr = [];
          return this.pros.filter(pro => {
            // return arr.push(pro.name).includes(this.search);
            return arr.push(pro.name).includes(search);
          });
        }
      }
    };
    console.log("가", arr);
  }
};
</script>

<style>
section {
  width: 500px;
  height: 200px;
  border: 1px solid black;
  margin: 10px;
}
img {
  width: 100px;
  height: 100px;
}
input {
  margin: 10px;
  width: 500px;
  height: 50px;
  border: 2px solid black;
}
</style>
