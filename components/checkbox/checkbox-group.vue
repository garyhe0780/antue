<template>
  <div :class="prefixCls">
    <slot>
      <checkbox
        v-for="(item,index) in items"
        :key="index"
        v-model="item.checked"
        :disabled="disable(item)"
        :class="prefixCls+'-item'"
        @change="change">{{ item.label }}
      </checkbox>
    </slot>
  </div>
</template>

<script>
  import Checkbox from './checkbox'

  export default {
    name: 'checkboxGroup',
    components: { Checkbox },
    props: {
      disabled: {
        type: Boolean,
        default: false
      },
      options: {
        type: Array,
        default: () => []
      },
      prefixCls: {
        type: String,
        default: 'ant-checkbox-group'
      },
      value: {
        type: Array,
        default: () => []
      }
    },
    computed: {
      items () {
        return this.options.map(item => {
          const _item = item.constructor === String ? { label: item, value: item } : item
          return Object.assign({}, _item, { checked: this.value.indexOf(_item.value) > -1 })
        })
      }
    },
    methods: {
      change () {
        const value = this.items.filter(item => item.checked === true).map(item => item.value)
        this.$emit('input', value)
        this.$emit('change', value, this.items)
      },
      disable (item) {
        return this.disabled || item.disabled === true
      }
    }
  }
</script>
