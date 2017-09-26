<style lang="">
  .btn{
    padding: 6px 10px;
  }
</style>
<template>
    <div>
        这是第一个页面
        <ul>
            <li v-for="(item,index) in items" :key="index">
                {{ index }} . {{ item.desc }}
            </li>
        </ul>
        <button @click="changeArr()">点击</button>
        <ul v-show="newArr.length > 0">
			<li>这是新数组</li>
          	<li v-for="(item,index) in newArr" :key="index">{{ item.desc }}</li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'first',
  data () {
    return {
      items: [
        {
          desc: '这是一段很长很长的描述'
        },
        {
          desc: '这是一段很长很长的描述'
        },
        {
          desc: '这是一段很长很长的描述'
        }
      ],
      newArr: []
    }
  },
  methods: {
    changeArr () {
    }
  }
}
</script>