<template>
  <div :class="b()">
    <l-default>
      <c-product-list/>
    </l-default>
  </div>
</template>

<script>
  import lDefault from '@/components/l-default';
  import cProductList from '@/components/c-product-list';

  export default {
    name: 'product-list',
    components: {
      lDefault,
      cProductList,
    },
  };
</script>
