<template>
  <div class="search-bar">
    <div class="search-bar_serching">
      <div class="search-bar_input-container">
        <input class="search-bar_input" type="text" v-model="searchQuery" placeholder="Search VIN" />
        <img class="search-bar_icon" src="@/assets/zoom.png" alt="Search Icon" />
      </div>
      <label class="search-bar_select" for="itemsPerPage">Select vehicles per page:</label>
      <select id="itemsPerPage" v-model="itemsPerPage">
        <option :value="10">9</option>
        <option :value="20">12</option>
        <option :value="50">15</option>
      </select>
    </div>
    <div class="controls">
      <button class="controls_btn" @click="addNewProduct">
        <img class="controls_btn_img" src="@/assets/plus.png" alt="add">
        ADD VEHICLE
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  data() {
    return {
      searchQuery: '',
      itemsPerPage: 10,
    };
  },
  methods: {
    addNewProduct() {
      // 
      alert("Новая карточка добавлена");
    },
  },
};
</script>

<style scoped>
.search-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 20px 30px;
  gap: 20px;
}

.search-bar_serching {
  display: flex;
  flex-direction: row;
}

.search-bar_input-container {
  position: relative;
  width: 334px;
}


.search-bar_input {
  width: 100%;
  border: 1px solid #e4e4e4;
  border-radius: 8px;
  padding: 9px 0 9px 16px;
  font-size: 16px;
  font-weight: 400;
  line-height: 22px;
}

.search-bar_icon {
  position: absolute;
  top: 50%;
  right: 6px;
  transform: translateY(-50%);
  width: 24px;
  height: 24px;
  pointer-events: none;
}


.search-bar_options {
  display: flex;
  align-items: center;
}

.search-bar_select {
  margin-left: 52px;
  padding-top: 11px;
}


#itemsPerPage {
  width: 85px;
  height: 42px;
  border: 1px solid #e4e4e4;
  border-radius: 8px;
  margin-left: 16px;
  font-family: DM Sans;
  font-size: 16px;
  font-weight: 400;
  line-height: 22px;
  text-align: left;
  color: #293148;
  padding: 9px 16px;
  appearance: none;
  background: url(@/assets/chevron_down.svg) no-repeat right;
  background-position-x: calc(100% - 10px);
}


.controls {
  display: flex;
  align-items: center;
}


.controls_btn {
  font-family: DM Sans;
  font-size: 12px;
  font-weight: 700;
  line-height: 20px;
  letter-spacing: 1px;
  color: #ffffff;
  background-color: #D90E32;
  width: 180px;
  height: 42px;
  padding: 9px 12px;
  border-radius: 10px;
  border: 1px solid #D90E32;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}


.controls_btn_img {
  width: 24px;
  height: 24px;
}
</style>