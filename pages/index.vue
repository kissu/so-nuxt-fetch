<template>
  <div>
    {{ opp }}
  </div>
</template>

<script>
export default {
  async asyncData({ params, error, $http }) {
    try {
      const res = await $http.$get(
        'https://jsonplaceholder.typicode.com/todos/1'
      )
      console.log('here we go', res)
      return { opp: res }
    } catch (err) {
      error({ statusCode: 404, message: `User not found, ${err}` })
    }
  },
}
</script>
