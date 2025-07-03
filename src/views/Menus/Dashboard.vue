<template>
  <admin-layout>
    <PageBreadcrumb :pageTitle="currentPageTitle" />
    <div class="grid grid-cols-12 gap-4 md:gap-6">
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <CountTabs1 />
      </div>
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <CountTabs2 />
      </div>
      <div class="col-span-12 space-y-6 xl:col-span-6">
        <StatistikPasienBaru />
      </div>
      <div class="col-span-12 space-y-6 xl:col-span-6">
        <StatistikPerawatanMedis />
      </div>
      <div class="col-span-12">
        <TablePasien />
      </div>
    </div>
  </admin-layout>
</template>

<script setup>
import AdminLayout from "../../components/layout/AdminLayout.vue";
import StatistikPasienBaru from "@/components/dashboard/StatistikPasienBaru.vue";
import StatistikPerawatanMedis from "@/components/dashboard/StatistikPerawatanMedis.vue";
import TablePasien from "@/components/dashboard/TablePasien.vue";
import CountTabs1 from "@/components/dashboard/CountTabs1.vue";
import CountTabs2 from "@/components/dashboard/CountTabs2.vue";
import PageBreadcrumb from "@/components/common/PageBreadcrumb.vue";
import { ref } from "vue";
const currentPageTitle = ref("Dashboard");
</script>
