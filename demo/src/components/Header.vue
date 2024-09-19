<template>
  <header class="shop-header">
    <div class="header-left">
      <h1>{{ productName }}</h1>
      <span>{{ productQuantity }}</span>
    </div>
    <div class="header-right">
      <button @click="addProduct">
        <img src="@/assets/add.png" alt="add">
      </button>
      <div class="user-info">
        <img src="@/assets/user_photo.png" alt="Avatar" class="avatar" /><!-- :src="user.avatar" -->
        <span class="username">{{ user.name }}</span>
      </div>
      <div class="select-language">
        <img :src="languageIcons[selectedLanguage]" :alt="selectedLanguage">
        <select v-model="selectedLanguage">
          <option value="us">EN</option>
          <option value="uk">UK</option>
          <option value="de">DE</option>
          <option value="pt">PT</option>
        </select>
      </div>
    </div>
  </header>
</template>


<script>

import ukflag from '@/assets/uk.png';
import usflag from '@/assets/us.png';
import ptflag from '@/assets/pt.png';
import deflag from '@/assets/de.png';

export default {
  name: 'Header',
  props: {
    productName: String,
    productQuantity: Number,
    user: Object,
  },
  data() {
    return {
      selectedLanguage: 'uk',
      languageIcons: {
        uk: ukflag,
        us: usflag,
        pt: ptflag,
        de: deflag,
      },
    };
  },
  methods: {
    addProduct() {
      // Логика для добавления продукта
      alert("Добавлен новый продукт");
    },
  },
};
</script>

<style scoped>
.shop-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ffffff;
  border-bottom: 1px solid #e4e4e4;
  height: 102px;
}

.header-left {
  display: flex;
  justify-content: baseline;
}

.header-left h1 {
  margin-left: 30px;
  margin-top: 34px;
  font-size: 32px;
  font-weight: 700;
  line-height: 38px;
  text-align: left;

}

.header-left span {
  display: inline-block;
  width: auto;
  height: auto;
  margin-left: 18px;
  margin-bottom: 34px;
  border-radius: 6px;
  padding: 4px 14px 4px 14px;
  margin-top: 38px;
  gap: 10px;
  background-color: #F3F6F8;
  font-size: 15px;
  font-weight: 700;
  line-height: 22px;
  text-align: center;
  color: #293148CC;
}

.header-right {
  display: flex;
  align-items: center;
  margin-top: 2px;
}

.header-right button {

  padding: 0;
  background-color: #ffffff;
  border: none;
  width: 42px;
  height: 42px;
}

.user-info {
  margin-left: 40px;
  display: flex;
  justify-content: center;
}

.avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  margin-right: 10px;
}

.username {
  margin-top: 11px;
  font-size: 15px;
  font-weight: 500;
  line-height: 22px;
  text-align: left;

}

.select-language {
  display: flex;
  justify-content: center;
  margin-right: 20px;
}

.select-language img {
  margin-left: 30px;
  width: 24px;
  height: 24px;
}

.select-language select {
  border: none;
  font-size: 15px;
  font-weight: 500;
  line-height: 22px;
  text-align: left;
  margin-left: 10px;
}
</style>