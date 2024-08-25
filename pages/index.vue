<script setup lang="ts">
import type { PlanDetails } from "../types/planDetail";
let planDetailBasic: PlanDetails = {
  name: "Basic",
  price: {
    monthly: 19.99,
    yearly: 199.99,
  },
  options: {
    Storage: " 500 GB",
    UsersNumber: 2,
    dataSent: 3,
  },
};

let planDetailPro: PlanDetails = {
  name: "Professional",
  price: {
    monthly: 24.99,
    yearly: 249.99,
  },
  options: {
    Storage: "1 TB",
    UsersNumber: 5,
    dataSent: 10,
  },
};

let planDetailMaster: PlanDetails = {
  name: "Master",
  price: {
    monthly: 39.99,
    yearly: 399.99,
  },
  options: {
    Storage: "2 TB",
    UsersNumber: 10,
    dataSent: 20,
  },
};
</script>

<template>
  <section>
    <TheHeader />
    <TogglePlan />
  </section>
  <section class="flex flex-col items-center justify-center lg:flex-row">
    <!-- first plan -->
    <PriceCard :plan-detail="planDetailBasic" class="text-mediumGray">
      <template #button>
        <button
          class="hover:bg-blue-500 text-blue-700 hover:text-white border-blue-500 mt-3 w-[100%] rounded border bg-gradient-to-r from-skyBlue to-softViolet px-4 py-1 font-semibold text-mist transition-all duration-300 ease-in-out hover:scale-[1.05]"
        >
          LEARN MORE
        </button>
      </template>
    </PriceCard>
    <!-- second plan -->
    <PriceCard
      :plan-detail="planDetailPro"
      class="scale-[1] bg-gradient-to-br from-skyBlue to-softViolet text-[#fefefe] shadow-card-shadow lg:scale-[1.05]"
    >
      <template #button>
        <button
          class="hover:bg-blue-500 text-blue-700 hover:text-white border-blue-500 mt-3 w-[100%] rounded border bg-mist px-4 py-1 font-semibold text-softViolet transition-all duration-300 ease-in-out hover:scale-[1.05]"
        >
          LEARN MORE
        </button>
      </template>
    </PriceCard>
    <!-- third plan -->
    <PriceCard :plan-detail="planDetailMaster" class="text-mediumGray">
      <template #button>
        <button
          class="hover:bg-blue-500 text-blue-700 hover:text-white border-blue-500 mt-3 w-[100%] rounded border bg-mist bg-gradient-to-r from-skyBlue to-softViolet px-4 py-1 font-semibold text-mist transition-all duration-300 ease-in-out hover:scale-[1.05]"
        >
          LEARN MORE
        </button>
      </template>
    </PriceCard>
  </section>
</template>

<style scoped></style>
