<template>
  <div class="Hey-User">
    <p style="color: #ffa14e;" id="Hey-User" > 👋 Hey User</p>

    <p id="Your-dummy-dashboard">Your dummy dashboard</p>

        <q-btn-dropdown
        split
        rounded-borders
        class="no-shadow"
        no-caps
        label="Last 30 days">

        <!-- Last 30 days Drop Down -->
        <q-list>
          <q-item clickable v-close-popup>
              <q-item-section avatar>
                <q-avatar icon="today" color="info" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Last 1 week</q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="done" color="#ecccff" />
              </q-item-section>
          </q-item>

          <q-item clickable v-close-popup>
              <q-item-section avatar>
                <q-avatar icon="event" color="info" text-color="white" />
              </q-item-section>
              <q-item-section>
                <q-item-label>Last 24 hours</q-item-label>
              </q-item-section>
              <q-item-section side>
                <q-icon name="done" color="#ecccff" />
              </q-item-section>
          </q-item>
        </q-list>
      </q-btn-dropdown>
  </div>


</template>

<script>
export default {
  name: 'PageIndex'
}
</script>
