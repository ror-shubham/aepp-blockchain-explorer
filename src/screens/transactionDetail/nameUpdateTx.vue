<template>
  <div>

    <field v-if='transaction.tx.nameHash' name="Name Hash">
      <ae-hash type='short' :hash='transaction.tx.nameHash'/>
      <view-and-copy :text='transaction.tx.nameHash' />
    </field>

    <field v-if='transaction.tx.nameTtl' name="Name TTL">
      {{transaction.tx.nameTtl}}
    </field>

    <div v-if='transaction.tx.pointers'>
      <h2>Pointers</h2>
      <field :name="`${key}`" :key="key" v-for='(pointer, key) in transaction.tx.pointers'>
        <ae-hash type='short' :hash='pointer' />
        <view-and-copy :text='pointer'/>
      </field>
    </div>

  </div>
</template>
<script>
import Field from '../../components/field'
import AeHash from '../../components/aeHash'
import ViewAndCopy from '../../components/viewAndCopy'

export default {
  name: 'name-update-tx',
  components: { Field, AeHash, ViewAndCopy },
  props: ['transaction']
}
</script>
