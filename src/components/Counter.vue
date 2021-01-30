<template>
  <div>
    <h1 style="font-size: 100px">Countdown Vue App</h1>
    <span> {{ displayDays }} : </span>
    <span> {{ displayHours }} : </span>
    <span> {{ displayMinutes }} : </span>
    <span> {{ displaySeconds }} </span>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data: () => ({
    displayDays: 0,
    displayHours: 0,
    displayMinutes: 0,
    displaySeconds: 0,
  }),
  computed: {
    _seconds: () => {
      return 1000;
    },
    _minutes() {
      return this._seconds * 60;
    },
    _hours() {
      return this._minutes * 60;
    },
    _days() {
      return this._hours * 24;
    },
  },
  mounted() {
    this.showRemaining();
  },
  methods: {
    formatNum: (num) => (num < 10 ? "0" + num : num),
    showRemaining() {
      const timer = setInterval(() => {
        const now = new Date();
        const end = new Date(2022, 5, 3, 2, 10, 10, 10);
        const distance = end.getTime() - now.getTime();

        // if the timer end
        if (distance < 0) {
          clearInterval(timer);
          return;
        }

        const days = Math.floor(distance / this._days);
        const hours = Math.floor((distance % this._days) / this._hours);
        const minutes = Math.floor((distance % this._hours) / this._minutes);
        const seconds = Math.floor((distance % this._minutes) / this._seconds);

        // display countdown
        this.displayDays = this.formatNum(days);
        this.displayHours = this.formatNum(hours);
        this.displayMinutes = this.formatNum(minutes);
        this.displaySeconds = this.formatNum(seconds);
      }, 1000);
    },
  },
};
</script>

<style lang="scss" scoped>
span {
  font-size: 80px;
}
</style>
