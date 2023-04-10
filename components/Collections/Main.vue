<template>

  <!-- Login details  -->
  <div class="m-5">
    <div
      class="box-border h-20 w-full p-6 border-2 border-black flex justify-between"
    >
      <div class="flex">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          strokeWidth="{1.5}"
          stroke="currentColor"
          className="w-6 h-6"
        >
          <path
            strokeLinecap="round"
            strokeLinejoin="round"
            d="M16.5 8.25V6a2.25 2.25 0 00-2.25-2.25H6A2.25 2.25 0 003.75 6v8.25A2.25 2.25 0 006 16.5h2.25m8.25-8.25H18a2.25 2.25 0 012.25 2.25V18A2.25 2.25 0 0118 20.25h-7.5A2.25 2.25 0 018.25 18v-1.5m8.25-8.25h-6a2.25 2.25 0 00-2.25 2.25v6"
          />
        </svg>

        <h1>Vue</h1>
      </div>

      <div class="border-solid border-2 border-black p-2 h-10">
        <h1>Login: Purnima</h1>
      </div>
    </div>

    <!-- Search & Add Details section -->

    <div
      class="box-border h-96 w-full p-6 border-2 border-black flex justify-between"
    >
      <div class="flex justify-between">
        <div>
          <div class="mb-3 xl:w-96">
            <div class="relative mb-4 flex w-full flex-wrap items-stretch">
              <input
                type="search"
                class="relative m-0 block  min-w-0 flex-auto rounded border border-solid border-neutral-300 bg-transparent bg-clip-padding px-3 py-1.5 text-base font-normal text-neutral-700 outline-none transition duration-300 ease-in-out focus:border-primary-600 focus:text-neutral-700 focus:shadow-te-primary focus:outline-none dark:border-neutral-600 dark:text-neutral-200 dark:placeholder:text-neutral-200"
                placeholder="Search"
                aria-label="Search"
                aria-describedby="button-addon2"
              />

              <!--Search icon-->
              <span
                class="input-group-text flex items-center whitespace-nowrap rounded px-3 py-1.5 text-center text-base font-normal text-neutral-700 dark:text-neutral-200"
                id="basic-addon2"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                  class="h-5 w-5"
                >
                  <path
                    fill-rule="evenodd"
                    d="M9 3.5a5.5 5.5 0 100 11 5.5 5.5 0 000-11zM2 9a7 7 0 1112.452 4.391l3.328 3.329a.75.75 0 11-1.06 1.06l-3.329-3.328A7 7 0 012 9z"
                    clip-rule="evenodd"
                  />
                </svg>
              </span>
              <div class="m-5">
                <CollectionsList @editProject="editProject" />
              </div>

              <div class="m-5">
                <CollectionsEdit   />
              </div>
              
            </div>
          </div>
        </div>

        
      </div>

      <div>
        <button
          type="button"
          class="rounded bg-indigo-50 px-2 py-1 text-sm font-semibold shadow-sm hover:bg-indigo-100"
          @click="openModal()"
        >
          Add Details
        </button>
      </div>

      
    </div>

    <CollectionsAdd :addModal="addModal" @addData="addData"/>
  </div>
</template>

<script setup>
import { ref } from "vue";

const addModal = ref(false);

const openModal = () => {
  addModal.value = true;
} 

const addData=(details:any)=>{

      localStorage.setItem("employeeData", JSON.stringify(details));
    }

</script>
