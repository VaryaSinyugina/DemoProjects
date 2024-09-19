<template>
  <div class="pagination">
    <span class="pagination_pages">Showing {{ displayed }} out of {{ total }}</span>
    <div class="page-controls">
      <button @click="prevPage" :disabled="currentPage === 1">
        <img src="@/assets/chevron_left.png" alt="back">
      </button>
      <span class="page-controls_curr-page">{{ currentPage }}</span>
      <span class="page-controls_of">of</span>
      <span class="page-controls_total">{{ totalPages }}</span>
      <button @click="nextPage" :disabled="currentPage === totalPages">
        <img src="@/assets/chevron_right.png" alt="next">
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Pagination',
  props: {
    displayed: Number,
    total: Number,
  },
  data() {
    return {
      currentPage: 1,
      totalPages: this.total === 1 ? 1 : Math.ceil(this.total / this.displayed),
    };
  },
  methods: {
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
        this.$emit('page-changed', this.currentPage);
      }
    },
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
        this.$emit('page-changed', this.currentPage);
      }
    },
  },
};
</script>

<style scoped>
.pagination {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
  margin-left: 30px;
}

.pagination_pages {
  font-size: 16px;
  font-weight: 400;
  line-height: 22px;
  text-align: left;
  color: #293148CC;
}

.page-controls {
  display: flex;
  align-items: center;
}

.page-controls_curr-page,
.page-controls_total {
  border: 1px solid #e4e4e4;
  border-radius: 6px;
  width: 32px;
  height: 27px;
  text-align: center;
  color: #293148CC;
  font-size: 15px;
  font-weight: 400;
  line-height: 22px;
  padding-top: 5px;
}

.page-controls_of {
  color: #293148CC;
  font-size: 13px;
  font-weight: 400;
  line-height: 24px;
  text-align: center;
  margin-right: 12px;
  margin-left: 12px;
}

.page-controls button {
  margin: 0 10px;
  border: none;
  background-color: #ffffff;
}
</style>