<template>

  
<div class="q-pa-md">
  <div class="row">


      <div class="Hey-User">

          <div class="column1">
              <!-- 👋 Het User Text -->
              <p style="color: #ffa14e;" id="Hey-User" > 👋 Hey User</p>

              <!-- Your Dummy Dahsboard Text -->
              <p id="Your-dummy-dashboard">Your dummy dashboard</p>



              <!-- Last 30 Days Drop Down  -->
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


              <!-- Chart Container Section -->
              <div class="Charts">
                  <!-- Last 30 Days Bar Graph -->
                  <div class="Days-Chart">
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

                  <!-- Chat Section Containing Success Rate & Payment Issues -->
                  <div class="Charts-2">

                    <!-- Success Rate Chart -->
                    <div id="Success-Rate">Charts will render here</div>

                    <!-- Payment Issues Chart -->
                    <div id="Payment-Issues-Chart">Charts will render here</div>

                  </div>

              </div>
          
          </div>


          <!-- Chat Stats & Message Tab  -->
          <div class="column2">
              <div class="q-pa-md" style="max-width: 600px">
                <q-card>

                    <q-tabs
                      v-model="tab"
                      dense
                      class="text-grey"
                      active-color="primary"
                      indicator-color="primary"
                      align="justify">



                      <q-tab name="mails" label="Mails" />
                      <q-tab name="alarms" label="Alarms" />
                    </q-tabs>

                    <q-separator />

                  <q-tab-panels v-model="tab" animated>

                    <q-tab-panel name="mails" class="q-pa-none">

                        <q-splitter
                          v-model="splitterModel"
                          style="height: 250px">
                          

                          <template v-slot:before>
                            <q-tabs
                              v-model="innerTab"
                              vertical
                              class="text-teal"
                            >
                              <q-tab name="innerMails" icon="mail" label="Mails" />
                              <q-tab name="innerAlarms" icon="alarm" label="Alarms" />
                              <q-tab name="innerMovies" icon="movie" label="Movies" />
                            </q-tabs>
                          </template>

                          <template v-slot:after>
                            <q-tab-panels
                              v-model="innerTab"
                              animated
                              transition-prev="slide-down"
                              transition-next="slide-up"
                            >
                              <q-tab-panel name="innerMails">
                                <div class="text-h4 q-mb-md">Mails</div>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                              </q-tab-panel>

                              <q-tab-panel name="innerAlarms">
                                <div class="text-h4 q-mb-md">Alarms</div>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                              </q-tab-panel>

                              <q-tab-panel name="innerMovies">
                                <div class="text-h4 q-mb-md">Movies</div>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis praesentium cumque magnam odio iure quidem, quod illum numquam possimus obcaecati commodi minima assumenda consectetur culpa fuga nulla ullam. In, libero.</p>
                              </q-tab-panel>
                            </q-tab-panels>
                          </template>

                        </q-splitter>
                    </q-tab-panel>

                    <q-tab-panel name="alarms">
                      <div class="text-h6">Alarms</div>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    </q-tab-panel>

                  </q-tab-panels>
                </q-card>
              </div>

          </div>

      </div>


  </div>
</div>




</template>



<script>

// Dependencies
import Vue from 'vue';
import VueFusionCharts from 'vue-fusioncharts';
import FusionCharts from 'fusioncharts';
import Column2D from 'fusioncharts/fusioncharts.charts';
import FusionTheme from 'fusioncharts/themes/fusioncharts.theme.fusion';

Vue.use(VueFusionCharts, FusionCharts, Column2D, FusionTheme);





// Last 30 Days Chart
// A JSON Object To Store The Chart Configurations
const chartData = [
  {
    label: "Mar 1-7",
    value: "50",
    color: "#ecccff",
    plotSpacePercent: "95",
  },
  {
    label: "Mar 8-14",
    value: "125",
    color: "#ecccff"
  },
  {
    label: "Mar 15-21",
    value: "125",
    color: "#ecccff"
  },
  {
    label: "Mar 22-28",
    value: "125",
    color: "#ecccff"
  },
  {
    label: "Final wk",
    value: "190",
    color: "#ecccff"
  }
];
// Last 30 Days Chart
// Chart Configurations
const dataSource = {
  chart: {
    numbersuffix: "000",
    theme: "fusion",
    borderRadius: "45",
    borderColor: "#969696",
    taskBarBorderRadius: "65",
    showBorder: "1",
    chartTopMargin: "44",
    chartBottomMargin: "36",
    baseFont: "Montserrat",
    "baseFontSize": "14",
    
    
  },
  data: chartData
  };


// Success Rate Chart Configurations
FusionCharts.ready(function() {
  var revenueChart = new FusionCharts({
    type: 'doughnut2d',
    renderAt: 'Success-Rate',
    width: '344',
    height: '364',
    dataFormat: 'json',
    dataSource: {
      "chart": {
        "caption": "Success Rate",
        "subCaption": "Last year",
        "numberPrefix": "$",
        "bgColor": "#ffffff",
        "startingAngle": "310",
        "borderRadius": "45",
        "bgColor": "#ffffff",
            borderRadius: "45",
    borderColor: "#969696",
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


// Payment Issues Chart Configurations
FusionCharts.ready(function() {
  var salesAnlysisChart = new FusionCharts({
    type: 'mscombi2d',
    renderAt: 'Payment-Issues-Chart',
    width: '700',
    height: '400',
    dataFormat: 'json',
    dataSource: {
      "chart": {
        "caption": "Harry's SuperMart",
        "subCaption": "Sales analysis of last year",
        "xAxisname": "Month",
        "yAxisName": "Amount (In USD)",
        "numberPrefix": "$",
        "divlineColor": "#999999",
        "divLineIsDashed": "1",
        "divLineDashLen": "1",
        "divLineGapLen": "1",
        "toolTipColor": "#ffffff",
        "toolTipBorderThickness": "0",
        "toolTipBgColor": "#000000",
        "toolTipBgAlpha": "80",
        "toolTipBorderRadius": "2",
        "toolTipPadding": "5",
        "theme": "fusion"
      },
      "categories": [{
        "category": [{
            "label": "Jan"
          },
          {
            "label": "Feb"
          },
          {
            "label": "Mar"
          },
          {
            "label": "Apr"
          },
          {
            "label": "May"
          },
          {
            "label": "Jun"
          },
          {
            "label": "Jul"
          },
          {
            "label": "Aug"
          },
          {
            "label": "Sep"
          },
          {
            "label": "Oct"
          },
          {
            "label": "Nov"
          },
          {
            "label": "Dec"
          }
        ]
      }],
      "dataset": [{
          "seriesName": "Actual Revenue",
          "showValues": "1",
          "data": [{
              "value": "16000"
            },
            {
              "value": "20000"
            },
            {
              "value": "18000"
            },
            {
              "value": "19000"
            },
            {
              "value": "15000"
            },
            {
              "value": "21000"
            },
            {
              "value": "16000"
            },
            {
              "value": "20000"
            },
            {
              "value": "17000"
            },
            {
              "value": "25000"
            },
            {
              "value": "19000"
            },
            {
              "value": "23000"
            }
          ]
        },
        {
          "seriesName": "Projected Revenue",
          "renderAs": "line",
          "data": [{
              "value": "15000"
            },
            {
              "value": "16000"
            },
            {
              "value": "17000"
            },
            {
              "value": "18000"
            },
            {
              "value": "19000"
            },
            {
              "value": "19000"
            },
            {
              "value": "19000"
            },
            {
              "value": "19000"
            },
            {
              "value": "20000"
            },
            {
              "value": "21000"
            },
            {
              "value": "22000"
            },
            {
              "value": "23000"
            }
          ]
        },
        {
          "seriesName": "Profit",
          "renderAs": "area",
          "data": [{
              "value": "4000"
            },
            {
              "value": "5000"
            },
            {
              "value": "3000"
            },
            {
              "value": "4000"
            },
            {
              "value": "1000"
            },
            {
              "value": "7000"
            },
            {
              "value": "1000"
            },
            {
              "value": "4000"
            },
            {
              "value": "1000"
            },
            {
              "value": "8000"
            },
            {
              "value": "2000"
            },
            {
              "value": "7000"
            }
          ]
        }
      ]
    }
  }).render();
});

export default {
  name: 'PageIndex',
    data() {
    return {
      "type": "column2d",
      "renderAt": "chart-container",
      "width": "747",
      "height": "332",
      "dataFormat": "json",
      "FillColor": "red",
      

      // Chat Section
      tab: 'mails',
      innerTab: 'innerMails',
      splitterModel: 20,
      dataSource
    }
  },


}
</script>
