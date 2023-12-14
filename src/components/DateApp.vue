<template>
  <div class="Body">
    <div class="Content">
      Date: {{ date.toString() }}
      <br />
      Day: {{ getDay() }}
      <br />
      Month: {{ getMonth() }}
      <br />
      <div class="buttons">
        <button @click="addDay(1)">Add Day</button>
        <button @click="addMonth(1)">Add Month</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      date: new Date(),
    };
  },
  methods: {
    getDay() {
      return this.date.getDate();
    },
    getMonth() {
      return this.date.getMonth() + 1;
    },
    addDay(numberOfDays) {
      const newDate = new Date(this.date);
      newDate.setDate(newDate.getDate() + numberOfDays);
      this.date = newDate;
    },
    addMonth(numberOfMonths) {
      const newDate = new Date(this.date);
      newDate.setMonth(newDate.getMonth() + numberOfMonths);
      this.date = newDate;
    },
  },
};
</script>

<style scoped>
.Body {
  text-align: center;
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}
.Content {
  line-height: 50px;
  font-size: 20px;
}
.buttons {
    display: flex;
    flex-direction: row;
    gap: 20px;
    justify-content: center;
}
button{
    padding: 10px;
    border: none;
    background-color: rgba(0, 0, 0, 0.667);
    border-radius: 10px;
    color: white;
    cursor: pointer;
    font-size: 20px;
}
</style>
