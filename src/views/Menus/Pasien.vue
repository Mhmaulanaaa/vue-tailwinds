<template>
  <admin-layout>
    <PageBreadcrumb :pageTitle="currentPageTitle" />

    <div
      class="rounded-2xl border border-gray-200 bg-white p-5 dark:border-gray-800 dark:bg-white/[0.03] lg:p-6"
    >
      <div class="grid grid-cols-12 gap-4 md:gap-6">
        <div class="col-span-12">
          <ListPasien />
        </div>
      </div>
    </div>
  </admin-layout>
</template>

<script setup>
import AdminLayout from "../../components/layout/AdminLayout.vue";
import PageBreadcrumb from "@/components/common/PageBreadcrumb.vue";
import ListPasien from "@/components/menupasien/ListPasien.vue";
import { ref } from "vue";
const currentPageTitle = ref("Pasien");
</script>
