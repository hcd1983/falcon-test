<template>
  <div class="flex flex-col min-h-screen">
    <div class="border-b border-gray-300">
      <slot name="header" />
    </div>
    <div class="flex border-b border-gray-300 flex-1">
      <div class="w-[300px] border-r border-gray-300">
        <slot name="side" />
      </div>
      <div class="flex-1">
        <slot name="main" />
      </div>
    </div>
    <div>
      <slot name="footer"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Layout'
};
</script>
