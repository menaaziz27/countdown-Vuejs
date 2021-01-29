<template>
  <div>
    {{ displayDays }}
    {{ displayHours }}
    {{ displayminutes }}
    {{ displaySeconds }}
  </div>
</template>

<script>
export default {
  name: "Counter",
  data: () => ({
    displayDays: 0,
    displayHours: 0,
    displayminutes: 0,
    displaySeconds: 0,
  }),
};
</script>

<style lang="scss" scoped></style>
