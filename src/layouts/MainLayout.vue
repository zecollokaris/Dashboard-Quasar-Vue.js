<template>
    <q-layout view="lHh lpr lFf" class="shadow-2 rounded-borders">

              <q-header bordered class="bg-white text-primary">
                <!-- MENU BAR -->
                <!-- Menu Bar Containing (Search, Live, Language Menu, Notificaton & User) -->
                <q-toolbar class="Navigation-Menu">
                  
                  <q-toolbar-title>

                      <!-- Search Input -->
                      <div class="Search-Input">
                        <q-input
                          rounded standout="bg-teal text-white"
                          v-model="model"
                          label="Search"
                          bottom-slots
                          clear-icon="visible"
                          :error="!isValid">

                          <template v-slot:prepend>
                           <q-icon name="search" />
                          </template>
                        </q-input>
                        
                      </div>
                      <!-- Collapse Search Input -->

                      <!-- Toggle Switch -->
                      <q-toggle
                        class="Toggle"
                        v-model="value"
                        color="green"/>


                      <!-- Live -->
                      <p class="Live">Live</p>


                      <!-- Language Selector -->
                      <q-btn-dropdown class="Language-Selector" rounded no-caps label="English" dropdown-icon="expand_more">
                        <q-list>
                          <q-item clickable v-close-popup @click="onItemClick">

                            <q-item-section avatar>
                              <q-avatar style="font-size: 35px;" icon="record_voice_over " text-color="black" />
                            </q-item-section>

                            <q-item-section>
                              <q-item-label>Français</q-item-label>
                            </q-item-section>
                          </q-item>

                          <q-item clickable v-close-popup @click="onItemClick">
                            <q-item-section>
                              <q-item-label>Española</q-item-label>
                            </q-item-section>
                          </q-item>

                          <q-item clickable v-close-popup @click="onItemClick">
                            <q-item-section>
                              <q-item-label>Latino-Faliscan</q-item-label>
                            </q-item-section>
                          </q-item>
                        </q-list>
                      </q-btn-dropdown>
                      <!-- Collapse Language Selector -->

                      <!-- Notification Bell -->
                      <q-btn flat class="Notification" rounded-borders icon="circle_notifications" />
                      <p class="Notification-Alert">○</p>


                      <q-chip class="User" square>
                        <q-avatar class="User-Image">
                          <img class="U-Image" src="https://lh3.googleusercontent.com/-3kYQFYF2dd4/AAAAAAAAAAI/AAAAAAAAAAA/AMZuucmZAudpbrUg5jANwmcErD5lrjnTqA/photo.jpg?sz=46">
                        </q-avatar>
                        <p class="User-Name">User Name</p>
                        <p class="User-Id">test</p>
                        <q-icon class="User-Selector" name="expand_more" />
                      </q-chip>

                  </q-toolbar-title>
                  <q-btn
                    flat
                    dense
                    round
                    icon="menu"
                    aria-label="Menu"
                    @click="leftDrawerOpen = !leftDrawerOpen"/>

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

                  
                <!-- PAYMENT SECTION -->
                <!-- Payment Expansion Item -->
                <q-expansion-item
                    class="Title-Payments"
                    label="Payments"
                    default-opened>
                    
                    <q-card class="Card-Payments">

                        <q-card-section>
                          <!-- Payment Section Links -->
                          <!-- Contains Links in Payment Section -->
                          <EssentialLink
                            class="Group-3"
                            v-for="link in essentialLinks"
                            :key="link.title"
                            v-bind="link"/>
                        </q-card-section>

                    </q-card>

                </q-expansion-item>
                  <!-- COLLAPSE PAYMENT SECTION -->


                <!-- Border Line Above Commerce -->
                <div class="Line-2"></div>


                <!-- COMMERCE SECTION -->
                <!-- Commerce Expansion Item -->
                <q-expansion-item
                  class="Title-Commerce"
                  label="Commerce"
                  default-opened>
                  

                    <q-card class="Card-Commerce" >
                      
                          <q-card-section >
                      
                            <!-- Border Line Below Commerce -->
                            <div class="Line-3"></div>
                            

                            <!-- Commerce Menu Items -->
                            <div class="Commerce">

                                <!-- Refferrals Menu-->
                                <q-item to="/referrals" clickable v-ripple>
                                  <q-item-section avatar>
                                    <q-icon name="group_work" />
                                  </q-item-section>
                                  <q-item-section>Referrals</q-item-section>
                                </q-item>


                                <!-- Audit Logs Menu-->
                                <q-item to="/audit log" clickable v-ripple>
                                  <q-item-section avatar>
                                    <q-icon name="visibility" />
                                  </q-item-section>
                                  <q-item-section>Audit logs</q-item-section>
                                </q-item>


                                <!-- Settings Menu-->
                                <q-item to="/setting" clickable v-ripple>
                                  <q-item-section avatar>
                                    <q-icon name="settings" />
                                  </q-item-section>
                                  <q-item-section>Settings</q-item-section>
                                </q-item>

                            </div>
                            
                          </q-card-section>

                    </q-card>
                    
                </q-expansion-item>
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
      essentialLinks: linksData,
      tab: 'images',
      model: '',
      value: true
    }
  },

  // Search Input
  computed: {
    isValid () {
      return this.model.length <= 3
    }
  },

  methods: {
    onItemClick () {
      // console.log('Clicked on an Item')
    }
  }


}
</script>