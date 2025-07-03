<template>
  <div
    class="overflow-hidden rounded-2xl border border-gray-200 bg-white px-4 pb-3 pt-4 dark:border-gray-800 dark:bg-white/[0.03] sm:px-6"
  >
    <div class="flex flex-col gap-2 mb-4 sm:flex-row sm:items-center sm:justify-between">
      <h3 class="text-lg font-semibold text-gray-800 dark:text-white/90">
        Alamat dan Kontak
      </h3>
    </div>
    <!-- Checkbox -->
    <div class="flex flex-wrap items-center gap-8 mb-6">
      <div x-data="{ checkboxToggleTwo: true }">
        <label
          for="checkboxLabelTwo"
          class="flex cursor-pointer items-center text-sm font-medium text-gray-700 select-none dark:text-gray-400"
        >
          <div class="relative">
            <input
              type="checkbox"
              id="checkboxLabelTwo"
              class="sr-only"
              @change="checkboxToggleTwo = !checkboxToggleTwo"
            />
            <div
              :class="
                checkboxToggleTwo
                  ? 'border-brand-500 bg-brand-500'
                  : 'bg-transparent border-gray-300 dark:border-gray-700'
              "
              class="hover:border-brand-500 dark:hover:border-brand-500 mr-3 flex h-5 w-5 items-center justify-center rounded-md border-[1.25px] border-brand-500 bg-brand-500"
            >
              <span :class="checkboxToggleTwo ? '' : 'opacity-0'" class="">
                <svg
                  width="14"
                  height="14"
                  viewBox="0 0 14 14"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M11.6666 3.5L5.24992 9.91667L2.33325 7"
                    stroke="white"
                    stroke-width="1.94437"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </span>
            </div>
          </div>
          Pasien Baru
        </label>
      </div>
      <div x-data="{ checkboxToggleTwo: true }">
        <label
          for="checkboxLabelTwo"
          class="flex cursor-pointer items-center text-sm font-medium text-gray-700 select-none dark:text-gray-400"
        >
          <div class="relative">
            <input
              type="checkbox"
              id="checkboxLabelTwo"
              class="sr-only"
              @change="checkboxToggleTwo = !checkboxToggleTwo"
            />
            <div
              :class="
                checkboxToggleTwo
                  ? 'border-brand-500 bg-brand-500'
                  : 'bg-transparent border-gray-300 dark:border-gray-700'
              "
              class="hover:border-brand-500 dark:hover:border-brand-500 mr-3 flex h-5 w-5 items-center justify-center rounded-md border-[1.25px] border-brand-500 bg-brand-500"
            >
              <span :class="checkboxToggleTwo ? '' : 'opacity-0'" class="">
                <svg
                  width="14"
                  height="14"
                  viewBox="0 0 14 14"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M11.6666 3.5L5.24992 9.91667L2.33325 7"
                    stroke="white"
                    stroke-width="1.94437"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                </svg>
              </span>
            </div>
          </div>
          Pasien Lama
        </label>
      </div>
      <!-- End Checkbox -->
    </div>

    <form>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <!-- 1 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1"
            >Nomor Induk Kependudukan</label
          >
          <input
            type="text"
            placeholder="Masukkan No Induk Kependudukan"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 2 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">No Identitas Lain</label>
          <input
            type="email"
            placeholder="Masukkan No Identitas Lain"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 3 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Nama Pasien</label>
          <input
            type="tel"
            placeholder="Masukkan Nama Pasien"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
      </div>
      <!-- End Grid -->
      <div class="grid grid-cols-1 md:grid-cols-4 gap-4 mt-5">
        <!-- 1 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Tempat Lahir</label>
          <input
            type="text"
            placeholder="Masukkan Tempat Lahir"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 2 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Tanggal Lahir</label>
          <input
            type="date"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 3 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Umur</label>
          <input
            type="number"
            placeholder="Masukkan Umur"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 4 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Jenis Kelamin</label>
          <div class="relative">
            <select
              id="gender-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Jenis Kelamin</option>
              <option value="Laki-laki">Laki-laki</option>
              <option value="Perempuan">Perempuan</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
      </div>
      <!-- End Grid -->
      <div class="grid grid-cols-1 md:grid-cols-4 gap-4 mt-5">
        <!-- 1 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Anak Ke</label>
          <input
            type="text"
            placeholder="Masukkan Anak Ke"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 2 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Dari</label>
          <input
            type="text"
            placeholder="Masukkan Dari"
            class="w-full p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent"
          />
        </div>
        <!-- 3 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Status Perkawinan</label>
          <div class="relative">
            <select
              id="married-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Status Perkawinan</option>
              <option value="Kawin">Kawin</option>
              <option value="Belum Kawin">Belum Kawin</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <!-- 4 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Pekerjaan</label>
          <div class="relative">
            <select
              id="job-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Pekerjaan</option>
              <option value="Wiraswasta">Wiraswasta</option>
              <option value="Pegawai Negeri Sipil">Pegawai Negeri Sipil</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
      </div>
      <!-- End Grid -->
      <div class="grid grid-cols-1 md:grid-cols-5 gap-4 mt-5">
        <!-- 1 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Agama</label>
          <div class="relative">
            <select
              id="agama-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Agama</option>
              <option value="Islam">Islam</option>
              <option value="Kristen">Kristen</option>
              <option value="Hindu">Hindu</option>
              <option value="Buddha">Buddha</option>
              <option value="Konghuchu">Konghuchu</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <!-- 2 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Bahasa</label>
          <div class="relative">
            <select
              id="bahasa-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Bahasa</option>
              <option value="Indonesia">Bahasa Indonesia</option>
              <option value="Inggris">Bahasa Inggris</option>
              <option value="Mandarin">Bahasa Mandarin</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <!-- 3 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Warga Negara</label>
          <div class="relative">
            <select
              id="warganegara-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Warga Negara</option>
              <option value="Indonesia">Warga Negara Indonesia</option>
              <option value="Asing">Warga Negara Asing</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <!-- 4 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Suku</label>
          <div class="relative">
            <select
              id="suku-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Suku</option>
              <option value="Jawa">Jawa</option>
              <option value="Sunda">Sunda</option>
              <option value="Batak">Batak</option>
              <option value="Minangkabau">Minangkabau</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
        <!-- 5 -->
        <div>
          <label class="block text-gray-600 font-medium mb-1">Pendidikan</label>
          <div class="relative">
            <select
              id="pendidikan-select"
              class="appearance-none w-full p-3 border border-gray-300 rounded-lg bg-white focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent text-gray-700"
              onchange="rotateIcon()"
            >
              <option value="">Pilih Pendidikan</option>
              <option value="SD">SD</option>
              <option value="SMP">SMP</option>
              <option value="SMA">SMA</option>
              <option value="S1">S1</option>
              <option value="S2">S2</option>
              <option value="S3">S3</option>
            </select>

            <!-- Icon Dropdown -->
            <div
              class="absolute inset-y-0 right-3 flex items-center pointer-events-none transition-transform duration-300"
              id="dropdown-icon"
            >
              <svg
                class="w-5 h-5 text-gray-500"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                ></path>
              </svg>
            </div>
          </div>
        </div>
      </div>
      <!-- End Grid -->
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      checkboxToggleOne: true,
      checkboxToggleTwo: false,
    };
  },
};
</script>
