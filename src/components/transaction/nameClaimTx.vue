<template>
  <div>
    <div class="grid">
      <field name="account">
        <router-link :to='"/account/" + transaction.tx.account'>
          <named-address :address='transaction.tx.account'/>
        </router-link>
      </field>
      <field name="name">
        {{transaction.tx.name}}
      </field>
      <field name="name_salt">
        {{transaction.tx.name_salt}}
      </field>
    </div>
  </div>
</template>
<script>
import Field from '../field'
import NamedAddress from '../namedAddress'

export default {
  name: 'name-claim-tx',
  components: { Field, NamedAddress },
  props: [
    'transaction'
  ]
}
</script>
