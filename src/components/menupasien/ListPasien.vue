<template>
  <div
    class="overflow-hidden rounded-2xl border border-gray-200 bg-white px-4 pb-3 pt-4 dark:border-gray-800 dark:bg-white/[0.03] sm:px-6"
  >
    <div class="flex flex-col gap-2 mb-4 sm:flex-row sm:items-center sm:justify-between">
      <div>
        <h3 class="text-lg font-semibold text-gray-800 dark:text-white/90">
          Daftar Pasien
        </h3>
      </div>

      <div class="flex items-center gap-3">
        <button
          class="inline-flex items-center gap-2 rounded-lg border border-gray-300 bg-white px-4 py-2.5 text-theme-sm font-medium text-gray-700 shadow-theme-xs hover:bg-gray-50 hover:text-gray-800 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-white/[0.03] dark:hover:text-gray-200"
        >
          <svg
            class="stroke-current fill-white dark:fill-gray-800"
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M2.29004 5.90393H17.7067"
              stroke=""
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M17.7075 14.0961H2.29085"
              stroke=""
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M12.0826 3.33331C13.5024 3.33331 14.6534 4.48431 14.6534 5.90414C14.6534 7.32398 13.5024 8.47498 12.0826 8.47498C10.6627 8.47498 9.51172 7.32398 9.51172 5.90415C9.51172 4.48432 10.6627 3.33331 12.0826 3.33331Z"
              fill=""
              stroke=""
              stroke-width="1.5"
            />
            <path
              d="M7.91745 11.525C6.49762 11.525 5.34662 12.676 5.34662 14.0959C5.34661 15.5157 6.49762 16.6667 7.91745 16.6667C9.33728 16.6667 10.4883 15.5157 10.4883 14.0959C10.4883 12.676 9.33728 11.525 7.91745 11.525Z"
              fill=""
              stroke=""
              stroke-width="1.5"
            />
          </svg>

          Filter
        </button>

        <button
          class="inline-flex items-center gap-2 rounded-lg border border-gray-300 bg-white px-4 py-2.5 text-theme-sm font-medium text-gray-700 shadow-theme-xs hover:bg-gray-50 hover:text-gray-800 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-white/[0.03] dark:hover:text-gray-200"
        >
          See all
        </button>
      </div>
    </div>

    <div class="max-w-full overflow-x-auto custom-scrollbar">
      <table class="min-w-full">
        <thead>
          <tr class="border-t border-gray-100 dark:border-gray-800">
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                Nama
              </p>
            </th>
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                DPJP
              </p>
            </th>
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                Tanggal Penaftaran
              </p>
            </th>
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                Nomor Ruangan
              </p>
            </th>
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                Diagnosis
              </p>
            </th>
            <th class="py-3 text-left">
              <p class="font-medium text-gray-500 text-theme-xs dark:text-gray-400">
                Status
              </p>
            </th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(data, index) in datas"
            :key="index"
            class="border-t border-gray-100 dark:border-gray-800"
          >
            <td class="py-3 whitespace-nowrap">
              <div class="flex items-center gap-3">
                <div class="h-[50px] w-[50px] overflow-hidden rounded-md">
                  <img :src="data.image" :alt="data.name" />
                </div>
                <div>
                  <p class="font-medium text-gray-800 text-theme-sm dark:text-white/90">
                    {{ data.name }}
                  </p>
                  <span class="text-gray-500 text-theme-xs dark:text-gray-400"
                    >Nomor RM : {{ data.noRm }}
                  </span>
                </div>
              </div>
            </td>
            <td class="py-3 whitespace-nowrap">
              <p class="text-gray-500 text-theme-sm dark:text-gray-400">
                {{ data.dpjp }}
              </p>
            </td>
            <td class="py-3 whitespace-nowrap">
              <p class="text-gray-500 text-theme-sm dark:text-gray-400">
                {{ data.tglPendaftaran }}
              </p>
            </td>
            <td class="py-3 whitespace-nowrap">
              <p class="text-gray-500 text-theme-sm dark:text-gray-400">
                {{ data.nomorRuangan }}
              </p>
            </td>
            <td class="py-3 whitespace-nowrap">
              <p class="text-gray-500 text-theme-sm dark:text-gray-400">
                {{ data.diagnosis }}
              </p>
            </td>
            <td class="py-3 whitespace-nowrap">
              <span
                :class="{
                  'rounded-full px-2 py-0.5 text-theme-xs font-medium': true,
                  'bg-success-50 text-success-600 dark:bg-success-500/15 dark:text-success-500':
                    data.status === 'Sukses',
                  'bg-warning-50 text-warning-600 dark:bg-warning-500/15 dark:text-orange-400':
                    data.status === 'Proses',
                  'bg-error-50 text-error-600 dark:bg-error-500/15 dark:text-error-500':
                    data.status === 'Batalkan',
                }"
              >
                {{ data.status }}
              </span>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="border-t border-gray-200 px-6 py-4 dark:border-gray-800">
      <div class="flex items-center justify-between">
        <button
          class="text-theme-sm shadow-theme-xs flex items-center gap-2 rounded-lg border border-gray-300 bg-white px-2 py-2 font-medium text-gray-700 hover:bg-gray-50 hover:text-gray-800 sm:px-3.5 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-white/[0.03] dark:hover:text-gray-200"
        >
          <svg
            class="fill-current"
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M2.58301 9.99868C2.58272 10.1909 2.65588 10.3833 2.80249 10.53L7.79915 15.5301C8.09194 15.8231 8.56682 15.8233 8.85981 15.5305C9.15281 15.2377 9.15297 14.7629 8.86018 14.4699L5.14009 10.7472L16.6675 10.7472C17.0817 10.7472 17.4175 10.4114 17.4175 9.99715C17.4175 9.58294 17.0817 9.24715 16.6675 9.24715L5.14554 9.24715L8.86017 5.53016C9.15297 5.23717 9.15282 4.7623 8.85983 4.4695C8.56684 4.1767 8.09197 4.17685 7.79917 4.46984L2.84167 9.43049C2.68321 9.568 2.58301 9.77087 2.58301 9.99715C2.58301 9.99766 2.58301 9.99817 2.58301 9.99868Z"
              fill=""
            ></path>
          </svg>

          <span class="hidden sm:inline"> Previous </span>
        </button>

        <span
          class="block text-sm font-medium text-gray-700 sm:hidden dark:text-gray-400"
        >
          Page 1 of 10
        </span>

        <ul class="hidden items-center gap-0.5 sm:flex">
          <li>
            <a
              href="#"
              class="bg-brand-500/[0.08] text-theme-sm text-brand-500 hover:bg-brand-500/[0.08] hover:text-brand-500 dark:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium"
            >
              1
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              2
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              3
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              ...
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              8
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              9
            </a>
          </li>

          <li>
            <a
              href="#"
              class="text-theme-sm hover:bg-brand-500/[0.08] hover:text-brand-500 dark:hover:text-brand-500 flex h-10 w-10 items-center justify-center rounded-lg font-medium text-gray-700 dark:text-gray-400"
            >
              10
            </a>
          </li>
        </ul>

        <button
          class="text-theme-sm shadow-theme-xs flex items-center gap-2 rounded-lg border border-gray-300 bg-white px-2 py-2 font-medium text-gray-700 hover:bg-gray-50 hover:text-gray-800 sm:px-3.5 dark:border-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:hover:bg-white/[0.03] dark:hover:text-gray-200"
        >
          <span class="hidden sm:inline"> Next </span>

          <svg
            class="fill-current"
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M17.4175 9.9986C17.4178 10.1909 17.3446 10.3832 17.198 10.53L12.2013 15.5301C11.9085 15.8231 11.4337 15.8233 11.1407 15.5305C10.8477 15.2377 10.8475 14.7629 11.1403 14.4699L14.8604 10.7472L3.33301 10.7472C2.91879 10.7472 2.58301 10.4114 2.58301 9.99715C2.58301 9.58294 2.91879 9.24715 3.33301 9.24715L14.8549 9.24715L11.1403 5.53016C10.8475 5.23717 10.8477 4.7623 11.1407 4.4695C11.4336 4.1767 11.9085 4.17685 12.2013 4.46984L17.1588 9.43049C17.3173 9.568 17.4175 9.77087 17.4175 9.99715C17.4175 9.99763 17.4175 9.99812 17.4175 9.9986Z"
              fill=""
            ></path>
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const datas = ref([
  {
    name: "Jens Brincker",
    noRm: 1789462,
    image: "/images/photos/PxDewCoNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "27/02/2025",
    nomorRuangan: 120,
    diagnosis: "Flu",
    status: "Sukses",
  },
  {
    name: "Vanessa Cain",
    noRm: 1589466,
    image: "/images/photos/PxDewCeNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "01/03/2025",
    nomorRuangan: 125,
    diagnosis: "Demam",
    status: "Proses",
  },
  {
    name: "Allen Atkinson",
    noRm: 1789476,
    image: "/images/photos/PxLansCoNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "01/03/2025",
    nomorRuangan: 130,
    diagnosis: "Flu",
    status: "Sukses",
  },
  {
    name: "Sumaya Roach",
    noRm: 1589456,
    image: "/images/photos/PxLansCeNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "02/03/2025",
    nomorRuangan: 135,
    diagnosis: "Flu",
    status: "Batalkan",
  },
  {
    name: "Matthew Roberson",
    noRm: 1789466,
    image: "/images/photos/PxanakCoNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "03/03/2025",
    nomorRuangan: 140,
    diagnosis: "Flu",
    status: "Sukses",
  },
  {
    name: "Benedict Roth",
    noRm: 1789476,
    image: "/images/photos/PxanakCeNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "04/03/2025",
    nomorRuangan: 145,
    diagnosis: "Flu",
    status: "Sukses",
  },
  {
    name: "Lila Hammond ",
    noRm: 1789466,
    image: "/images/photos/PxbayiNewW.png",
    dpjp: "Dr.Kenny Josh",
    tglPendaftaran: "05/03/2025",
    nomorRuangan: 150,
    diagnosis: "Flu",
    status: "Sukses",
  },
]);
</script>
