<!-- OtherComponent.vue -->
<template>
    <div>
        <nav class="navbar bg-body-tertiary">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">
      <img src="https://th.bing.com/th/id/OIP.KDwcobfbRmFzJ83lCy3PvQHaH-?pid=ImgDet&rs=1" alt="Logo" width="30" height="24" class="d-inline-block align-text-top">
      ร้านกาแฟ คาเฟ่ในสวน
    </a>
  </div>
</nav>
      <h1 class="text-center">ร้านที่ {{receivedIndex  }}</h1>
      <p class="text-center">ชื่อร้าน {{ receivedRestaurantName }}</p>
      <p class="text-center">ราคา: {{ receivedRestaurantPrice }}</p>
      <img :src="receivedRestaurantImagesP" alt="" srcset="">
  <br/>
<br>
      <button @click="goToHome">back</button>
    </div>
    
  </template>
  
  <script>
export default {
    data() {
  return {
    receivedRestaurantName: null,
    receivedRestaurantImagesP: null,
    receivedIndex: null,
    receivedRestaurantPrice: null, 
  };
},
  created() {
    // ใช้ $route.query เพื่อรับข้อมูลที่ถูกส่งผ่านคิวรี่พารามิเตอร์
    this.receivedRestaurantName = this.$route.query.restaurantName;
    this.receivedRestaurantImagesP = this.$route.query.restaurantImagesP;
    this.receivedIndex = parseInt(this.$route.query.index)+1 ;
    this.receivedRestaurantPrice = this.$route.query.restaurantPrice;
  },
 
  methods: {
    goToHome() {
      // ส่งค่าไปยังคอมโพเนนต์ Home.vue
      this.$router.push({ name: 'home' });
    },
  },
};
  </script>
  <style>
div {
  text-align: center;
  padding: 20px;
}

h1 {
  font-size: 24px;
}

p {
  font-size: 16px;
  margin-top: 10px;
}

img {
  max-width: 100%;
  height: auto;
  margin-top: 20px;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #007BFF;
  color: #fff;
  border: none;
  cursor: pointer;
  font-size: 16px;
  border-radius: 4px;
}

button:hover {
  background-color: #0056b3;
}

  </style>