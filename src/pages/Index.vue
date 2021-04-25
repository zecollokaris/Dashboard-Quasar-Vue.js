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
        <q-list class="DropDown-Text">
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

      <div class="Charts">
          <!-- Last 30 Days Bar Graph -->
          <div id="app">
            <div id="chart-container">
              <fusioncharts
              :type="type"
              :width="width"
              :height="height"
              :dataformat="dataFormat"
              :dataSource="dataSource">

              </fusioncharts>
            </div>
          </div>

          <div id="Success-Rate">FusionCharts will render here</div>

      </div>
  </div>





</template>

<script>

// Include Dependencies
import Vue from 'vue';
import VueFusionCharts from 'vue-fusioncharts';
import FusionCharts from 'fusioncharts';
import Column2D from 'fusioncharts/fusioncharts.charts';
import FusionTheme from 'fusioncharts/themes/fusioncharts.theme.fusion';

Vue.use(VueFusionCharts, FusionCharts, Column2D, FusionTheme);

FusionCharts.ready(function() {
  var revenueChart = new FusionCharts({
    type: 'doughnut2d',
    renderAt: 'Success-Rate',
    width: '550',
    height: '450',
    dataFormat: 'json',
    dataSource: {
      "chart": {
        "caption": "Split of Revenue by Product Categories",
        "subCaption": "Last year",
        "numberPrefix": "$",
        "bgColor": "#ffffff",
        "startingAngle": "310",
        "showLegend": "1",
        "defaultCenterLabel": "Total revenue: $64.08K",
        "centerLabel": "Revenue from $label: $value",
        "centerLabelBold": "1",
        "showTooltip": "0",
        "decimals": "0",
        "theme": "fusion"
      },
      "data": [{
          "label": "Food",
          "value": "28504"
        },
        {
          "label": "Apparels",
          "value": "14633"
        },
        {
          "label": "Electronics",
          "value": "10507"
        },
        {
          "label": "Household",
          "value": "4910"
        }
      ]
    }
  }).render();
});




const chartData = [
  {
    label: "Venezuela",
    value: "290"
  },
  {
    label: "Saudi",
    value: "260"
  },
  {
    label: "Canada",
    value: "180"
  },
  {
    label: "Iran",
    value: "140"
  },
  {
    label: "Russia",
    value: "115"
  },
  {
    label: "UAE",
    value: "100"
  },
  {
    label: "US",
    value: "30"
  },
  {
    label: "China",
    value: "30"
  }
];



// STEP 3: Configure your chart
const dataSource = {
  chart: {
    caption: "Countries With Most Oil Reserves [2017-18]",
    subcaption: "In MMbbl = One Million barrels",
    xaxisname: "Country",
    yaxisname: "Reserves (MMbbl)",
    numbersuffix: "K",
    theme: "fusion"
  },
  data: chartData
  };

export default {
  name: 'PageIndex',
    data() {
    return {
      "type": "column2d",
      "renderAt": "chart-container",
      "width": "550",
      "height": "350",
      "dataFormat": "json",
      dataSource
    }
  }
}
</script>
