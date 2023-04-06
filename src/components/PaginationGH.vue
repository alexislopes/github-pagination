<template>
  <div class="flex gap-2">

    <span class="previous">
      Previous
    </span>
    <span class="next">
      Next
    </span>
  </div>
</template>

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
  @apply text-[#2f81f7] flex items-center gap-1
}
</style>