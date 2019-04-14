<template>
    <Tabs type="card">
        <TabPane label="New Product">
          <ProductForm />
        </TabPane>
        <TabPane label="Product List">
          <ProductTable />
        </TabPane>
    </Tabs>
</template>
<script>
    import ProductForm from './components/ProductForm.vue'
    import ProductTable from './components/ProductTable.vue'
    export default {
      props: [],
      components: {
        ProductForm,
        ProductTable
      }
    }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
