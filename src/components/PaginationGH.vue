<template>
                          <div class="flex gap-1 h-fit items-center">

                            <span @click="prev" class="previous" :class="{ 'disabled': isFirstPage }">
                              Previous
                            </span>
                            <p v-for="page in pageCount" :class="{ 'active': currentPage === page }" @click="currentPage = page
                            "> {{ page }}</p>
                            <span @click="next" class="next" :class="{ 'disabled': isLastPage }">
      Next
    </span>
  </div>
</template>

<script setup>
import { useOffsetPagination } from '@vueuse/core'
import { ref } from 'vue'

const data = ref([1, 2, 3, 4, 5, 6, 7, 8])

const {
  currentPage,
  currentPageSize,
  pageCount,
  isFirstPage,
  isLastPage,
  prev,
  next,
} = useOffsetPagination({
  total: data.value.length,
  page: 1,
  pageSize: 2,
})

</script>

<style scoped>
.previous::before {
  clip-path: polygon(9.8px 12.8px, 8.7px 12.8px, 4.5px 8.5px, 4.5px 7.5px, 8.7px 3.2px, 9.8px 4.3px, 6.1px 8px, 9.8px 11.7px, 9.8px 12.8px);
  display: inline-block;
  width: 16px;
  height: 16px;
  vertical-align: text-bottom;
  content: "";
  background: #2f81f7;
}

.next::after {
  clip-path: polygon(6.2px 3.2px, 7.3px 3.2px, 11.5px 7.5px, 11.5px 8.5px, 7.3px 12.8px, 6.2px 11.7px, 9.9px 8px, 6.2px 4.3px, 6.2px 3.2px);
  display: inline-block;
  width: 16px;
  height: 16px;
  vertical-align: text-bottom;
  content: "";
  background: #2f81f7;
}

span {
  @apply text-[#2f81f7] flex items-center gap-1 cursor-pointer select-none border border-transparent px-3 py-2 rounded
}


.next.disabled,
.previous.disabled {
  @apply text-[#484f58]
}

.next.disabled::after,
.previous.disabled::before {
  @apply bg-[#484f58] 
}

p {
  @apply text-white px-3 py-2 leading-5 cursor-pointer rounded border border-transparent h-fit transition-[border] delay-75
}

p:hover,
span:hover {
  @apply border border-[#30363d] box-border h-fit
}

span.disabled:hover {
  @apply border-transparent
}

.active {
  @apply bg-[#1f6feb] text-white text-center rounded border-transparent
}

.active:hover {
  @apply border-transparent
}
</style>