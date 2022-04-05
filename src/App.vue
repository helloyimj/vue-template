<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <div v-if="count > 4">
    4보다 큽니다!
  </div>
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruit"
      :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>

<script>
import Fruit from '~/comments/Fruit'

export default {
  components: {
    Fruit
    // Fruit: Fruit // 객체 데이터 내부의 속성의 이름과 데이터의 이름이 같으면 생략 가능
  },
  data() {
    return {
      count: 0,
      fruits: ['Apple', 'Banana', 'Cherry']
    }
  },
  methods: {
    increase() {
      this.count += 1
    }
  }

}
</script>

<style lang="scss">
h1 {
  font-size: 50px;
  color: royalblue;
}
ul {
  li {
    font-size: 40px;
  }
}
</style>