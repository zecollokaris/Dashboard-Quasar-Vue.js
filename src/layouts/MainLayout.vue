<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <!-- DRAWER -->
    <!-- Drawer Containing Side Bar -->
    <q-drawer
      class="Bar"
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1">
      
      <!-- SIDE BAR -->
      <!-- This Is The Side Bar Menu Containing Menu Options -->
      <q-list class="Sidebar">

        <!-- Title Test -->
        <q-item-label
          header
          class="Test">
          Test
        </q-item-label>

      <q-expansion-item
        
        dense-toggle
        switch-toggle-side
        icon="perm_identity"
        label="Account settings">
        
        <q-card>
          <q-card-section>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
            commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
            eveniet doloribus ullam aliquid.
          </q-card-section>
        </q-card>
      </q-expansion-item>

        <!-- PAYMENT SECTION -->
        <!-- Title Payment -->
        <div class="Group-12">
          <q-item-label
            header
            class="Payments">
            Payments <div class="Polygon-1">▼</div>
          </q-item-label>
        </div>

        <!-- Payment Section Links -->
        <!-- Contains Links in Payment Section -->
        <EssentialLink
          class="Group-3"
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"/>

        <!-- COLLAPSE PAYMENT SECTION -->


        <!-- COMMERCE SECTION -->
        <!-- Border Line Above Commerce -->
        <div class="Line-2"></div>

        <!-- Title Commerce -->
        <div class="Group-12">
          <q-item-label
            header
            style="margin-top: 4px;"
            class="Payments">
            Commerce <div class="Polygon-1">▲</div>
          </q-item-label>
        </div>

        <!-- Border Line Below Commerce -->
        <div class="Line-3"></div>
        

        <!-- Commerce Menu Items -->
        <div class="Commerce">

            <q-item to="/referrals" clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="group_work" />
              </q-item-section>

              <q-item-section>Referrals</q-item-section>
            </q-item>



            <q-item to="/audit log" clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="visibility" />
              </q-item-section>

              <q-item-section>Audit logs</q-item-section>
            </q-item>



            <q-item to="/setting" clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="settings" />
              </q-item-section>

              <q-item-section>Settings</q-item-section>
            </q-item>
        </div>
        <!-- COLLAPSE COMMERCE SECTION -->

        
        
      </q-list>
      <!-- COLLAPSE SIDE BAR -->

    </q-drawer>
    <!-- COLLAPSE DRAWER -->

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

// SIDE BAR MENU OPTION LINKS,TITLE AND ICONS
import EssentialLink from 'components/EssentialLink.vue'
const linksData = [
  {
    title: 'Transactions',
    icon: 'swap_horizontal_circle',
    link: '#transactions'
  },
  {
    title: 'Customers',
    icon: 'people',
    link: '#customers'
  },
  {
    title: 'Payouts',
    icon: 'payment',
    link: '#payouts'
  },
  {
    title: 'Balances',
    icon: 'account_balance_wallet',
    link: '#balances'
  },
  {
    title: 'Subscriptions',
    icon: 'offline_pin',
    link: '#subscriptions'
  },
  {
    title: 'Payment plans',
    icon: 'list',
    link: '#payment plans'
  }

];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
