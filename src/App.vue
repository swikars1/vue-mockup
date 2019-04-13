<template>
    <Tabs type="card">
        <TabPane label="New Product">
          <HelloWorld />
        </TabPane>
        <TabPane label="Product List">product list page</TabPane>
    </Tabs>
</template>
<script>
    import ProductForm from './components/ProductForm'
    export default {
        components: {
          ProductForm
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
