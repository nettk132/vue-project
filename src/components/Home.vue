<!-- Home.vue -->
<template>
    <nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img src="https://th.bing.com/th/id/OIP.KDwcobfbRmFzJ83lCy3PvQHaH-?pid=ImgDet&rs=1" alt="Logo" width="30" height="24" class="d-inline-block align-text-top">
      ร้านกาแฟ คาเฟ่ในสวน
    </a>
  </div>
</nav>
    <div class="container text-center">
      <div class="row">
        <div
          class="col mt-5"
          v-for="(restaurant, index) in travelList"
          :key="index"
        >
          <div class="card" style="width: 18rem">
            <img
              :src="restaurant.imagesP"
              class="card-img-top"
              :width="sizeW"
              :height="sizeH"
            />
            <div class="card-body">
              <h2>ร้านที่ : {{ index+1 }}</h2>
              <h5 class="card-title">ชื่อร้าน : {{ restaurant.Name }}</h5>
              <p class="card-text">ราคาเริ่ม : {{ restaurant.price }}</p>
              <button
                class="btn btn-danger"
                data-bs-toggle="modal"
                data-bs-target="#staticBackdrop"
                @click="goToOtherComponent(restaurant.Name, restaurant.imagesP,index)"
              >
                จองร้าน
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue'; // import ref
  
  export default {
    methods: {
      goToOtherComponent(Name, imagesP,index, price) {
        // ส่งค่าไปยังคอมโพเนนต์ OtherComponent.vue ผ่านคิวรี่พารามิเตอร์
        this.$router.push({
          name: 'other',
          query: {
            index:index,
            restaurantName: Name,
            restaurantImagesP: imagesP,
            restaurantPrice: price,
          },
        });
      },
    },
    setup() {
        const travelList = ref([
  {
    Name: "Patom Organic Living",
    price: 300,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    time: "",
    imagesP: "https://cms.dmpcdn.com/food/2021/01/14/419314c0-562c-11eb-b22e-fd8b6bde0acf_original.jpg",
  },
  {
    Name: "Hookrajong Cafe",
    price: 245,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    time: "",
    imagesP: "https://cms.dmpcdn.com/food/2021/01/14/40f463c0-562c-11eb-8350-b3a0991ba51b_original.jpg",
  },
  {
    Name: "Portobello & Désiré Cafe",
    price: 235,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    time: "",
    imagesP: "https://cms.dmpcdn.com/food/2022/01/09/34c2df70-710e-11ec-9ca0-bd1143265365_original.jpg",
  },
  {
    Name: "Wood Cafe",
    price: 600,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    time: "",
    imagesP: "https://cms.dmpcdn.com/food/2022/01/09/35f45a90-710e-11ec-9ca0-bd1143265365_original.jpg",
  },
]);
  
    
  
      return { // return ตัวแปรออกมาจาก setup
        travelList,
      
      };
    },
  };
  </script>
  <style>
.button{
  color: #000000;
  padding: 8px 22px;
  border-radius: 6px;
  background: #4dc61d;
  transition: all 0.2s ease;
  padding: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  
}
.button:active{
  transform: scale(0.96);
}


.ColShop {
  display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    justify-items: stretch;
    align-items: stretch;
    column-gap: 40px;
    row-gap: 40px;
    
    padding: 30px;
    
}



/* ปรับขนาดและสไตล์ */
.card {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  text-align: center;
}

.card-img-top {
  max-width: 100%;
  height:250px;
  transition: all 0.2 ease;
}
.card-img-top:active{
  transform: scale(0.96);
}
.boxCount {
    background-color: aliceblue;
    color: black;
    border-radius: 5px;
    box-shadow: 0px 0px 0px 1px rgba(0, 0, 0, 0.87);
    margin-bottom: 10px;
  }
  /* Style the table */
.table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

/* Style the total_text class */
.total_text {
  font-weight: bold;
}



/* Style the cancel button */
.cancle_bt {
  background-color: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
  transition: all 0.2 ease;
}
.cancle_bt:active{
  transform: scale(0.96);
}

/* Add hover effect to the cancel button */
.cancle_bt:hover {
  background-color: #ff1f00;
}

.card_body{
  padding: 5px;
  margin: 0;
}

.title{
  text-align: center;
  padding-bottom: 10px;
}

.c-item{
  height: 480px;
}

.c-item{
  height: 100%;
  object-fit: cover;
}
</style>