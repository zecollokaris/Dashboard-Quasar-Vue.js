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

                <div class="Chat">

                  <div class="Chat-Section">

                    <!-- Stats & Mesaage Slider Tab  -->
                    <q-tabs
                        v-model="tab"
                        align="justify"
                        narrow-indicator
                        class="Chat-Menu">
                        <q-tab name="mails" label="Stats" />
                        <q-tab name="alarms" label="Messages" />

                        <div class="LineChat"></div>
                        
                    </q-tabs>

                    <!-- Message & Stats Container Containing Messages -->
                    <div class="Bubble-Container">
                      

                      <!-- TAB PANEL -->
                      <q-tab-panels
                          v-model="tab"
                          animated
                          transition-prev="scale"
                          transition-next="jump-down"
                          class="Bubble">
                          
                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="mails">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #72c8cc;" :type="type" />
                                      <p id="James-Robinson">James Robinson</p>
                                      <p id="Bubble-Date">Jan 2, 12:31am</p>
                                      <p id="Text-Message">I need some maintenac...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>



                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="alarms">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #72c8cc;" :type="type" />
                                      <p id="James-Robinson">James Robinson</p>
                                      <p id="Bubble-Date">Jan 2, 12:31am</p>
                                      <p id="Text-Message">I need some maintenac...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>

                      </q-tab-panels>




                      <!-- TAB PANEL -->
                      <q-tab-panels
                          v-model="tab"
                          animated
                          transition-prev="jump-up"
                          transition-next="scale"
                          class="Bubble">

                          
                          
                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="mails">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #8e4b6e;" :type="type" />
                                      <p id="James-Robinson">Eseosa Igbinobaro</p>
                                      <p id="Bubble-Date">Wed 3, 06:00pm</p>
                                      <p id="Text-Message">I got your email ad and...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>



                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="alarms">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #8e4b6e;" :type="type" />
                                      <p id="James-Robinson">Eseosa Igbinobaro</p>
                                      <p id="Bubble-Date">Wed 3, 06:00pm</p>
                                      <p id="Text-Message">I got your email ad and...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>

                      </q-tab-panels>


                      <!-- TAB PANEL -->
                      <q-tab-panels
                          v-model="tab"
                          animated
                          transition-prev="scale"
                          transition-next="jump-down"
                          class="Bubble">
                          
                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="mails">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #72c8cc;" :type="type" />
                                      <p id="James-Robinson">James Robinson</p>
                                      <p id="Bubble-Date">Jan 2, 12:31am</p>
                                      <p id="Text-Message">I need some maintenac...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>


                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="alarms">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #72c8cc;" :type="type" />
                                      <p id="James-Robinson">James Robinson</p>
                                      <p id="Bubble-Date">Jan 2, 12:31am</p>
                                      <p id="Text-Message">I need some maintenac...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>

                      </q-tab-panels>



                      <!-- TAB PANEL -->
                      <q-tab-panels
                          v-model="tab"
                          animated
                          transition-prev="jump-up"
                          transition-next="scale"
                          class="Bubble">
                          
                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="mails">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #ffbb4f;" :type="type" />
                                      <p id="James-Robinson">Lupita Jonah</p>
                                      <p id="Bubble-Date">Jan 2, 12:31am</p>
                                      <p id="Text-Message">Thank you so much for...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>



                          <!-- Messages Card -->
                          <!-- Message Card Containing Message Display -->
                          <q-tab-panel class="Bubble-Card" name="alarms">
                              <div class="q-pa-md">
                                <div class="q-gutter-md row items-start">
                                  <q-card class="Bubble-Card" flat bordered v-for="type in skeletonTypes" :key="type" style="width: 250px">


                                    <q-card-section>
                                      <q-skeleton  style="width: 35px; height: 35px; background-color: #ffbb4f;" :type="type" />
                                      <p id="James-Robinson">Lupita Jonah</p>
                                      <p id="Bubble-Date">Feb 13, 06:15pm</p>
                                      <p id="Text-Message">Thank you so much for...</p>
                                      <q-icon id="Text-Vector" name="done_all" />
                                    </q-card-section>
                                  </q-card>
                                </div>
                              </div>
                          </q-tab-panel>

                      </q-tab-panels>

                    </div>

                  </div>

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





/* ############################################### */
// LAST 30 DAYS CHART
/* ############################################### */

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
    // Chart Design Config
    "chartLeftMargin": "55",
    "chartTopMargin": "44",
    "chartRightMargin": "50",
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
    "divLineDashed": "1",
    "divLineDashLen": "10",
    "divLineDashGap": "6"
    
    
  },
  data: chartData
  };







/* ############################################### */
// SUCCESS RATE CHART
/* ############################################### */

// Success Rate Chart Configurations
FusionCharts.ready(function() {
  var revenueChart = new FusionCharts({
    type: 'doughnut2d',
    renderAt: 'Success-Rate',
    width: '324',
    height: '354',
    dataFormat: 'json',
    dataSource: {
      "chart": {
        // Chart Design Config
        "caption": "Success Rate",
        captionFontSize: "16px",
        captionFontColor: "#333333",
        captionFontBold: "1",
        captionHorizontalPadding: "-150px",
        "bgColor": "#ffffff",
        "startingAngle": "180",
        "borderRadius": "45",
        "borderColor": "#969696",
        "centerLabel": "$value",
        "centerLabelBold": "1",
        "theme": "fusion",
        showLabels: 0,
        showValues: 0,
        showBorder: "1",
        centerLabelFontSize: "18px",
        centerLabelFont: "Montserrat",
        defaultcenterlabel:"98%",
        centerLabelColor: "#a6d997",
        baseFont: "Montserrat",
        "pieRadius": "105",
        "doughnutRadius": "65",
        "legendItemFontSize": "12",
        


      },
      "data": [{

          "label": "Unsuccessful",
          "value": "1",
          color: "#dfeedb"
        },
        {
          "label": "Successfull",
          "value": "150",
          color: "#a6d997"
        },

      ]
    }
  }).render();
});





/* ############################################### */
// PAYMENT ISSUES CHART
/* ############################################### */

// Payment Issues Chart Configurations
FusionCharts.ready(function() {
  var revenueChart = new FusionCharts({
    type: 'stackedcolumn2d',
    renderAt: 'Payment-Issues-Chart',
    width: '324',
    height: '354',
    dataFormat: 'json',
    dataSource: {
      "chart": {
        "theme": "fusion",
        "caption": "Payment Issues",
        "chartBottomMargin": "20",
        "chartRightMargin": "40",
        captionFontSize: "16px",
        baseFont: "Montserrat",
        //Showing the Cumulative Sum of stacked data
        "showSum": "1",
        showBorder: "1",
        "borderRadius": "45",
        "borderColor": "#969696",
        dashGap: "150px",
        "legendPosition": "bottom-left",
        "legendCaption": "Total number of errors: 19",
        "legendCaptionBold": "1",
        "legendCaptionFontSize": "14",
        "legendCaptionFontColor": "#ffa14e",
        "legendItemFontSize": "12",
        "legendItemFont": "Montserrat",
        "yAxisValueFontColor": "#ffffff",
        "divLineColor": "#ffffff",

      },
      "categories": [{
        "category": [{
            "label": "a",
            color: "#bdbdbd",
            fontsize: "12px"
          },
          {
            "label": "x",
            color: "#bdbdbd",
            fontsize: "12px"
          },
          {
            "label": "o",
            color: "#bdbdbd",
            fontsize: "12px"
          },
          {
            "label": "n",
            color: "#bdbdbd",
            fontsize: "12px"
          }
        ]
      }],
      "dataset": [{
          "seriesname": "Customer errors",
          color: "#ffbb4f",
          "data": [{
              "value": "1",
              color: "#ffbb4f"
            },
            {
              "value": "0",
              color: "#ffffff"
            },
            {
              "value": "0",
              color: "#ffffff"
            },
            {
              "value": "0",
              color: "#ffffff"
            }
          ]
        },
        {
          "seriesname": "Fraud blocks",
          color: "#ffda93",
          "data": [{
              "value": "0"
            },
            {
              "value": "5",
              color: "#ffda93"
            },
            {
              "value": "0"
            },
            {
              "value": "0"
            }
          ]
        },
        {
          "seriesname": "Bank errors",
          "data": [{
              "value": "0"
            },
            {
              "value": "0"
            },
            {
              "value": "3",
              color: "#ff7576"
            },
            {
              "value": "0"
            }
          ]
        },
        {
          "seriesname": "System errors",
          color: "#80e0e5",
          "data": [{
              "value": "0"
            },
            {
              "value": "0"
            },
            {
              "value": "0"
            },
            {
              "value": "10",
              color: "#80e0e5"
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
      // Last 30 Days Chart Config
      "type": "column2d",
      "renderAt": "chart-container",
      "width": "747",
      "height": "332",
      "dataFormat": "json",
      

      // Message Section
      tab: 'mails',
      innerTab: 'innerMails',
      splitterModel: 20,
      dataSource,

      // Message Card
      skeletonTypes: [
         'QToggle'
      ]
    }
  },


}
</script>
