<style lang="">
  .btn{
    padding: 6px 10px;
    color:#fff;
    background: #ff5555;
    border: 0;
    outline: 0;
  }
  .btn:active{
      background: rgba(0,0,0,.7);
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
        <button class="btn" @click="changeArr()">点击</button>
        <ul v-show="newArr.length > 0">
			<li>这是新数组</li>
          	<li v-for="(item,index) in newArr" :key="index">{{ index }} . {{ item.desc }}</li>
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
            id: 1,
            desc: '这是一段很长很长的描述2'
        },
        {
            id: 2,            
            desc: '这是一段很长很长的描述1'
        },
        {
            id: 3,            
            desc: '这是一段很长很长的描述3'
        }
      ],
      newArr: []
    }
  },
  methods: {
    changeArr () {
        this.newArr = this.items.filter((item,index,arr) => {
            return index > 1;
        })
    }
  }
}
</script>