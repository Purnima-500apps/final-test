<template>
  <div>
    <div
      class="max-w-sm p-6 bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700"
    >
      <div class="flex justify-between">
        <div>
          <img
            class="rounded-full w-10 h-10"
            src="https://www.rd.com/wp-content/uploads/2021/04/GettyImages-988013222-scaled-e1618857975729.jpg"
            alt="image description"
          />
        </div>
        <div class="ml-5">
            <button @click="editModal" type="button" class="py-2.5 px-5 mr-2 mb-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700">EDIT</button>
            <button @click="deleteModal" type="button" class="text-white bg-gray-800 hover:bg-gray-900 focus:outline-none focus:ring-4 focus:ring-gray-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700">DELETE</button>

        </div>
      </div>
      <div class="mt-3">
        <h1>Name: Purnima</h1>
        <h1>Age: 0</h1>
        <h1>Date of Birth: 00 Aug 0000</h1>
      </div>
    </div>


    <CollectionsEdit :edit="edit"/>
    <CollectionsDelete :deleteData="deleteData"/>

    
    

  </div>

 
</template>
<script setup>
// const props = defineProps({ candidate: Object });
import {ref} from 'vue'
const edit = ref(false);
const deleteData = ref(false);

const emits = defineEmits(["edit"]);


const editModal = () => {
    edit.value=true;

    // emits("editProject", true);
};

const deleteModal =  () => {
    deleteData.value = true;
}

</script>
