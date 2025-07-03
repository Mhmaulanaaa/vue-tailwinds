<template>
  <admin-layout>
    <PageBreadcrumb :pageTitle="currentPageTitle" />
    <div class="grid grid-cols-12 gap-4 md:gap-6">
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <MenuTabs1 />
      </div>
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <MenuTabs2 />
      </div>
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <MenuTabs3 />
      </div>
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <MenuTabs4 />
      </div>
      <div class="col-span-6 space-y-6 xl:col-span-6">
        <MenuTabs5 />
      </div>
    </div>
  </admin-layout>
</template>

<script setup>
import AdminLayout from "../../components/layout/AdminLayout.vue";
import PageBreadcrumb from "@/components/common/PageBreadcrumb.vue";
import MenuTabs1 from "@/components/menumaster/MenuTabs1.vue";
import MenuTabs2 from "@/components/menumaster/MenuTabs2.vue";
import MenuTabs3 from "@/components/menumaster/MenuTabs3.vue";
import MenuTabs4 from "@/components/menumaster/MenuTabs4.vue";
import MenuTabs5 from "@/components/menumaster/MenuTabs5.vue";
import { ref } from "vue";
const currentPageTitle = ref("Menu Master");
</script>
