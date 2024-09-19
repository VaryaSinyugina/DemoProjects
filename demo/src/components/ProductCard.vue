<template>
  <div class="product-card">
    <button @click="">
      <img src="@/assets/dots.png" alt="open">
    </button>
    <img class="product-card_img" :src="car.photo.url" alt="Product Image" />
    <div class="product-card_main-information">
      <h3>{{ car.vehicle_name }}</h3>
      <p>{{ car.vin }}</p>
    </div>
    <div class="product-card_footer">
      <span>{{ car.angles_count }}/30</span>
      <p>{{ createdAt(car.created_at) }}</p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'ProductCard',
  props: {
    car: {
      type: Object,
      required: true
    }
  },
  methods: {
    createdAt(unixTimestamp) {
      const date = new Date(unixTimestamp * 1000);
      const today = new Date();

      today.setHours(0, 0, 0, 0);
      date.setHours(0, 0, 0, 0);

      const difference = today - date;
      const daysDifference = Math.floor(difference / (1000 * 60 * 60 * 24));

      if (daysDifference === 0) {
        return "today";
      } else {
        return `${daysDifference} days left`;
      }
    }
  }
};
</script>

<style scoped>
.product-card {
  display: flex;
  flex-direction: column;
  border-radius: 10px;
  background-color: #F3F6F8;
  margin: 15px;
  width: 354px;
  height: 335px;
}

.product-card button {
  width: 24px;
  height: 24px;
  border: none;
  background-color: #F3F6F8;
  margin-right: 20px;
  margin-top: 20px;
  margin-left: auto;
  display: flex;

}

.product-card_img {
  margin-left: 47px;
  max-width: 100%;
  width: 260px;
  height: 135px;
}

.product-card_main-information {
  border-bottom: 1px solid #e4e4e4;
  margin-left: 24px;
  margin-right: 24px;
}

.product-card_main-information h3 {
  font-size: 20px;
  font-weight: 700;
  line-height: 22px;
  text-align: left;
  color: #293148;

  margin-bottom: 0;
}

.product-card_main-information p {
  font-size: 15px;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0.30000001192092896px;
  text-align: left;
  color: #29314899;
  margin-top: 10px;
  ;
}

.product-card_footer {
  display: flex;
  justify-content: space-between;
  margin-top: 15px;
}

.product-card_footer span {
  width: auto;
  height: auto;
  margin-bottom: 16px;
  margin-top: 7px;
  margin-left: 24px;
  border-radius: 6px;
  background-color: #EDEDED;
  color: #293148CC;
  font-size: 15px;
  font-weight: 700;
  line-height: 22px;
  text-align: center;
  padding: 4px 14px 4px 14px;
}

.product-card_footer p {
  font-size: 15px;
  font-weight: 500;
  line-height: 16px;
  text-align: right;
  color: #29314899;
  margin-right: 24px;
  margin-bottom: 23px;
}
</style>