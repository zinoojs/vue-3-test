<template>
<div class="text-center m-auto">
    <h1 class="text-2xl py-4 font-bold">Calendar</h1>
    <section class="flex justify-between mx-3">
        <p class="font-semibold text-xl">{{ currentMonthName }}</p>
        <p class="font-semibold text-xl">{{ currentYear }}</p>
    </section>
    <section class="flex my-2">
        <p class=" text-center" style="width: 14.28%" v-for="day in days" :key="day">{{ day }}</p>
    </section>
    <section class="flex flex-wrap">
        <p class="text-center" style="width: 14.28%" v-for="num in startDay()" :key="num"></p>
        <p class="text-center" style="width: 14.28%" v-for="num in daysInMonth(currentYear,currentMonth)" :key="num">{{ num }}</p>
    </section>
</div>
  
</template>

<script>
export default {
    data() {
        return {
            currentMonthName : new Date().toLocaleString('default', { month: "long"}),
            currentMonth : new Date().getMonth() + 1,
            currentYear : new Date().getFullYear(),
            days : [ 'Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat']
        }
    },
    methods : {
        daysInMonth(year,month) {
            return new Date(year,month,0).getDate();
        },
        startDay() {
            return new Date( this.currentYear, this.currentMonth-1,1).getDay();
        }
    }
}
</script>

<style>

</style>