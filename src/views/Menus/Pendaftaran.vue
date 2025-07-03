<template>
  <admin-layout>
    <PageBreadcrumb :pageTitle="currentPageTitle" />

    <div
      class="rounded-2xl border border-gray-200 bg-white p-5 dark:border-gray-800 dark:bg-white/[0.03] lg:p-6"
    >
      <div>
        <PendaftaranBaru />
        <AlamatKontak class="mt-5" />
      </div>
    </div>
  </admin-layout>
</template>

<script setup>
import AdminLayout from "../../components/layout/AdminLayout.vue";
import PageBreadcrumb from "@/components/common/PageBreadcrumb.vue";
import PendaftaranBaru from "@/components/menupendaftaran/PendaftaranBaru.vue";
import AlamatKontak from "@/components/menupendaftaran/AlamatKontak.vue";
import { ref } from "vue";
const currentPageTitle = ref("Pendaftaran");
</script>
