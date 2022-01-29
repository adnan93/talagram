<template>
  <div class="home">
    <div id="nav">
      <br />
      <div style="text-align: center">
        <b class="mb-0" style="color: #0d5671">نرخ های امروز {{ today }} </b>
      </div>
      <br />

      <b-row class="d-flex justify-content-center" dir="rtl">
        <b-row class="background container mr-2">
          <b-col class="pl-0" cols="7">
            <b style="font-size: 0.8em">
              <img
                class="img-responsive mt-0 mb-0 pt-0 pb-0"
                width="20px"
                height="20px"
                src="@/assets/chart.png"
                alt="طلاگرام"
                @click="showChart()"
                title="نمودار"
                style="cursor: pointer"
              />

              <!-- <v-icon
                title="نمودار"
                class="ml-2"
                style="font-size: 15px; color: #f5d438"
                @click="showChart()"
                >insights</v-icon
              > -->

              <v-icon
                title="اطلاعات"
                class="ml-1"
                style="font-size: 18px; color: #f5d438"
                @click="showChart()"
                >info</v-icon
              >

              دلار
            </b>
          </b-col>

          <b-col cols="5">
            <b style="color: black">
              {{ numberWithCommas(dollar) }}
            </b>
          </b-col>
        </b-row>

        <b-row class="background container mr-2">
          <b-col class="pl-0" cols="8">
            <b style="font-size: 0.8em">
              <!-- <v-icon
                title="نمودار"
                class="ml-1"
                style="font-size: 1.3em; color: #f5d438"
                @click="showChart()"
                >show_chart</v-icon
              > -->

              <img
                class="img-responsive mt-0 mb-0 pt-0 pb-0"
                width="20px"
                height="20px"
                src="@/assets/chart.png"
                alt="طلاگرام"
                @click="showChart()"
                title="نمودار"
                style="cursor: pointer"
              />

              <v-icon
                title="اطلاعات"
                style="font-size: 18px; color: #f5d438"
                @click="showChart()"
                >info</v-icon
              >

              انس طلا
            </b>
          </b-col>

          <b-col cols="4">
            <b style="color: black"> {{ ons }} $ </b>
          </b-col>
        </b-row>

        <b-row class="background mr-2">
          <b-col class="pl-0" cols="8">
            <b style="font-size: 0.75em">
              <!-- <v-icon
                title="نمودار"
                class="ml-1"
                style="font-size: 1.3em; color: #f5d438"
                @click="showChart()"
                >show_chart</v-icon
              > -->
              <img
                class="img-responsive mt-0 mb-0 pt-0 pb-0"
                width="20px"
                height="20px"
                src="@/assets/chart.png"
                alt="طلاگرام"
                @click="showChart()"
                title="نمودار"
                style="cursor: pointer"
              />

              <v-icon
                title="اطلاعات"
                style="font-size: 18px; color: #f5d438"
                @click="showChart()"
                >info</v-icon
              >

              انس نقره
            </b>
          </b-col>

          <b-col cols="4">
            <b style="color: black"> {{ numberWithCommas(silver) }} $ </b>
          </b-col>
        </b-row>
      </b-row>

      <b-row>
        <b-col cols="1"> </b-col>

        <b-col cols="10">
          <b-row class="mb-4" dir="rtl" align="center">
            <b-col> </b-col>
          </b-row>

          <b-row dir="rtl">
            <b-col class="grid col-xl-4 col-lg-6 col-sm-12 col-12">
              <b-card-group dir="rtl">
                <b-card style="border-radius: 20px" class="shadow">
                  <template #header>
                    <div style="text-align: center">
                      <b
                        class="mb-0"
                        style="color: #ffffff; text-shadow: 3px 3px 7px black"
                        >نرخ طلا و سكه</b
                      >
                    </div>
                  </template>

                  <div>
                    <b-row align="right">
                      <b-col class="pl-0" cols="6">
                        <b>
                          <!-- <v-icon
                            title="نمودار"
                            class="ml-2"
                            style="font-size: 18px; color: #f5d438"
                            @click="showChart()"
                            >show_chart</v-icon
                          > -->

                          <img
                            class="img-responsive mt-0 mb-0 pt-0 pb-0"
                            width="20px"
                            height="20px"
                            src="@/assets/chart.png"
                            alt="طلاگرام"
                            @click="showChart()"
                            title="نمودار"
                            style="cursor: pointer"
                          />

                          <v-icon
                            title="اطلاعات"
                            class="ml-1"
                            style="font-size: 18px; color: #f5d438"
                            @click="showChart()"
                            >info</v-icon
                          >

                          آبشده
                        </b>
                      </b-col>

                      <b-col class="pr-0" cols="3">
                        <div v-if="mesghalPrice > 0">
                          <b style="color: green">
                            {{ numberWithCommas(mesghalPrice) }}%</b
                          >
                        </div>
                        <div v-else>
                          <b style="color: red">
                            ({{ numberWithCommas(mesghalPrice) }}%)</b
                          >
                        </div>
                      </b-col>
                      <b-col cols="3">
                        <b> {{ numberWithCommas(mesghalPrice) }} </b>
                      </b-col>
                    </b-row>
                    <br />
                    <br />

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب آبشده
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabAbshode > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabAbshode) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabAbshode) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabAbshode) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>

                  <hr />

                  <div>
                    <b-row align="right">
                      <b-col class="pl-0" cols="6">
                        <b>
                          <!-- <v-icon
                            title="نمودار"
                            class="ml-2"
                            style="font-size: 18px; color: #f5d438"
                            @click="showChart()"
                            >show_chart</v-icon
                          > -->

                          <img
                            class="img-responsive mt-0 mb-0 pt-0 pb-0"
                            width="20px"
                            height="20px"
                            src="@/assets/chart.png"
                            alt="طلاگرام"
                            @click="showChart()"
                            title="نمودار"
                            style="cursor: pointer"
                          />

                          <v-icon
                            title="اطلاعات"
                            class="ml-1"
                            style="font-size: 18px; color: #f5d438"
                            @click="showChart()"
                            >info</v-icon
                          >

                          سكه امامی
                        </b>
                      </b-col>

                      <b-col class="pr-0" cols="3">
                        <div v-if="sekePrice > 0">
                          <b style="color: green">
                            {{ numberWithCommas(sekePrice) }}%</b
                          >
                        </div>
                        <div v-else>
                          <b style="color: red">
                            ({{ numberWithCommas(sekePrice) }}%)</b
                          >
                        </div>
                      </b-col>
                      <b-col cols="3">
                        <b>
                          {{ numberWithCommas(sekePrice) }}
                        </b>
                      </b-col>
                    </b-row>

                    <br />
                    <br />

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب سكه امامی
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabSeke > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabSeke) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabAbshode) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabSeke) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            سكه بهار آزادی
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="sekeGhadimPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(sekeGhadimPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(sekeGhadimPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(sekeGhadimPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                      <br />
                    </div>

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب سكه بهار آزادی
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabSekeGhadim > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabSekeGhadim) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabSekeGhadim) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabSekeGhadim) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            نیم سکه
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="nimPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(nimPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(nimPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(nimPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                      <br />
                    </div>

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب نیم سکه
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabNim > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabNim) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabNim) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabNim) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            ربع سکه
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="robPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(robPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(robPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(robPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                      <br />
                    </div>

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب ربع سکه
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabRob > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabRob) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabRob) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabRob) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            سکه گرمی
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="sekeGeramiPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(sekeGeramiPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(sekeGeramiPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(sekeGeramiPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                      <br />
                    </div>

                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <div class="hob">
                            <!-- <v-icon
                              title="نمودار"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="mr-1"
                              style="font-size: 16px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            حباب سکه گرمی
                          </div>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="HobabGerami > 0">
                            <b style="color: green">
                              {{ numberWithCommas(HobabGerami) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(HobabGerami) }}%)</b
                            >
                          </div>
                        </b-col>
                        <b-col cols="3">
                          <b style="color: rgb(99, 51, 51)">
                            {{ numberWithCommas(HobabGerami) }}</b
                          >
                        </b-col>
                      </b-row>
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            نرخ طلای 18
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="geramTalaPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(geramTalaPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(geramTalaPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(geramTalaPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            نرخ طلای 24
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="gram24TalaPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(gram24TalaPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(gram24TalaPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(gram24TalaPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            ارزش طلای آبشده
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="mesghalRiyal > 0">
                            <b style="color: green">
                              {{ numberWithCommas(mesghalRiyal) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(mesghalRiyal) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(mesghalRiyal) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            ارزش طلای خام سكه تمام
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="sekeRiyal > 0">
                            <b style="color: green">
                              {{ numberWithCommas(sekeRiyal) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(sekeRiyal) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(mesghalRiyal) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                    </div>
                  </div>
                  <hr />

                  <div>
                    <div>
                      <b-row align="right">
                        <b-col class="pl-0" cols="6">
                          <b>
                            <!-- <v-icon
                              title="نمودار"
                              class="ml-2"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >show_chart</v-icon
                            > -->

                            <img
                              class="img-responsive mt-0 mb-0 pt-0 pb-0"
                              width="20px"
                              height="20px"
                              src="@/assets/chart.png"
                              alt="طلاگرام"
                              @click="showChart()"
                              title="نمودار"
                              style="cursor: pointer"
                            />

                            <v-icon
                              title="اطلاعات"
                              class="ml-1"
                              style="font-size: 18px; color: #f5d438"
                              @click="showChart()"
                              >info</v-icon
                            >

                            نرخ انس نقره
                          </b>
                        </b-col>

                        <b-col class="pr-0" cols="3">
                          <div v-if="silverPrice > 0">
                            <b style="color: green">
                              {{ numberWithCommas(silverPrice) }}%</b
                            >
                          </div>
                          <div v-else>
                            <b style="color: red">
                              ({{ numberWithCommas(silverPrice) }}%)</b
                            >
                          </div>
                        </b-col>

                        <b-col cols="3">
                          <b> {{ numberWithCommas(silverPrice) }} </b>
                        </b-col>
                      </b-row>
                      <br />
                    </div>
                  </div>
                </b-card>
              </b-card-group>
            </b-col>

            <b-col class="grid col-xl-4 col-lg-6 col-12">
              <b-card-group>
                <b-card dir="rtl" style="border-radius: 20px" class="shadow">
                  <template #header>
                    <div style="text-align: center" class="head1">
                      <b
                        class="mb-0"
                        style="color: #ffffff; text-shadow: 3px 3px 7px black"
                        >سکه بورسی</b
                      >
                    </div>
                  </template>
                  <div class="container">
                    <b-card-text>
                      <div>
                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <b style="font-size: 0.8em">
                                <!-- <v-icon
                                  title="نمودار"
                                  class="ml-2"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->
                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="ml-1"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                سکه یک روزه بانک رفاه
                              </b>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="sekeRefahPrice > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(sekeRefahPrice) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{ numberWithCommas(sekeRefahPrice) }}%)</b
                                >
                              </div>
                            </b-col>

                            <b-col cols="3">
                              <b> {{ numberWithCommas(sekeRefahPrice) }} </b>
                            </b-col>
                          </b-row>
                          <br />
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به بازار آزاد
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabRefahCoinFree > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(HobabRefahCoinFree) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabRefahCoinFree)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{ numberWithCommas(HobabRefahCoinFree) }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به طلای خام سكه
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabRefahCoinSekeRiyal > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabRefahCoinSekeRiyal)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabRefahCoinSekeRiyal)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{
                                  numberWithCommas(HobabRefahCoinSekeRiyal)
                                }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>
                      </div>
                      <hr />

                      <div>
                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <b style="font-size: 0.8em">
                                <!-- <v-icon
                                  title="نمودار"
                                  class="ml-2"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="ml-1"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                سکه یک روزه بانک صادرات
                              </b>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="sekeSaderatPrice > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(sekeSaderatPrice) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{ numberWithCommas(sekeSaderatPrice) }}%)</b
                                >
                              </div>
                            </b-col>

                            <b-col cols="3">
                              <b>
                                {{ numberWithCommas(sekeSaderatPrice) }}
                              </b>
                            </b-col>
                          </b-row>
                          <br />
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به بازار آزاد
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabRefahCoinFree > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabSaderatCoinFree)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabSaderatCoinFree)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{ numberWithCommas(HobabSaderatCoinFree) }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->
                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به طلای خام سكه
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabSaderatCoinSekeRiyal > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabSaderatCoinSekeRiyal)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabSaderatCoinSekeRiyal)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{
                                  numberWithCommas(HobabSaderatCoinSekeRiyal)
                                }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>
                      </div>
                      <hr />

                      <div>
                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <b style="font-size: 0.8em">
                                <!-- <v-icon
                                  title="نمودار"
                                  class="ml-2"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="ml-1"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                سکه یک روزه بانک ملت
                              </b>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="sekeMellatPrice > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(sekeMellatPrice) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{ numberWithCommas(sekeMellatPrice) }}%)</b
                                >
                              </div>
                            </b-col>

                            <b-col cols="3">
                              <b> {{ numberWithCommas(sekeMellatPrice) }} </b>
                            </b-col>
                          </b-row>
                          <br />
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به بازار آزاد
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabMellatCoinFree > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabMellatCoinFree)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabMellatCoinFree)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{ numberWithCommas(HobabMellatCoinFree) }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->

                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به طلای خام سكه
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabMellatCoinSekeRiyal > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabMellatCoinSekeRiyal)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabMellatCoinSekeRiyal)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{
                                  numberWithCommas(HobabMellatCoinSekeRiyal)
                                }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>
                      </div>
                      <hr />

                      <div>
                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <b style="font-size: 0.8em">
                                <!-- <v-icon
                                  title="نمودار"
                                  class="ml-2"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->
                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="ml-1"
                                  style="font-size: 18px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                سکه یک روزه بانک سامان
                              </b>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="sekeSamanPrice > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(sekeSamanPrice) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{ numberWithCommas(sekeSamanPrice) }}%)</b
                                >
                              </div>
                            </b-col>

                            <b-col cols="3">
                              <b> {{ numberWithCommas(sekeSamanPrice) }} </b>
                            </b-col>
                          </b-row>
                          <br />
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->
                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به بازار آزاد
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabSamanCoinFree > 0">
                                <b style="color: green">
                                  {{ numberWithCommas(HobabSamanCoinFree) }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabSamanCoinFree)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{ numberWithCommas(HobabSamanCoinFree) }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>

                        <div>
                          <b-row align="right">
                            <b-col class="pl-0" cols="6">
                              <div class="hob">
                                <!-- <v-icon
                                  title="نمودار"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >show_chart</v-icon
                                > -->
                                <img
                                  class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                  width="20px"
                                  height="20px"
                                  src="@/assets/chart.png"
                                  alt="طلاگرام"
                                  @click="showChart()"
                                  title="نمودار"
                                  style="cursor: pointer"
                                />

                                <v-icon
                                  title="اطلاعات"
                                  class="mr-1"
                                  style="font-size: 16px; color: #f5d438"
                                  @click="showChart()"
                                  >info</v-icon
                                >

                                حباب نسبت به طلای خام سكه
                              </div>
                            </b-col>

                            <b-col class="pr-0" cols="3">
                              <div v-if="HobabSamanCoinSekeRiyal > 0">
                                <b style="color: green">
                                  {{
                                    numberWithCommas(HobabSamanCoinSekeRiyal)
                                  }}%</b
                                >
                              </div>
                              <div v-else>
                                <b style="color: red">
                                  ({{
                                    numberWithCommas(HobabSamanCoinSekeRiyal)
                                  }}%)</b
                                >
                              </div>
                            </b-col>
                            <b-col cols="3">
                              <b style="color: rgb(99, 51, 51)">
                                {{
                                  numberWithCommas(HobabSamanCoinSekeRiyal)
                                }}</b
                              >
                            </b-col>
                          </b-row>
                        </div>
                      </div>
                    </b-card-text>
                  </div>
                </b-card>
              </b-card-group>
            </b-col>

            <b-col class="grid col-xl-4 col-12">
              <b-card-group dir="rtl">
                <b-card style="border-radius: 20px" class="shadow">
                  <template #header>
                    <div style="text-align: center">
                      <b
                        class="mb-0"
                        style="color: #ffffff; text-shadow: 3px 3px 7px black"
                        >صندوق طلا</b
                      >
                    </div>
                  </template>

                  <div class="container" style="background-color: Light">
                    <b-card-text>
                      <b-row class="test1" dir="rtl">
                        <div>
                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <b style="font-size: 0.8em">
                                  <!-- <v-icon
                                    title="نمودار"
                                    class="ml-2"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->
                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="ml-1"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  صندوق پشتوانه طلای لوتس (طلا)
                                </b>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaLotusPriceOpen > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaLotusPriceOpen)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaLotusPriceOpen)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>

                              <b-col cols="3">
                                <b>
                                  {{ numberWithCommas(talaLotusPriceOpen) }}
                                </b>
                              </b-col>
                            </b-row>
                            <br />
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به طلای خام سكه
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaLotusSeke > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(HobabTalaLotusSeke)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaLotusSeke)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaLotusSeke) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به NAV
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaLotusNav > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(HobabTalaLotusNav)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaLotusNav)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaLotusNav) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  مقدار NAV ابطال
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaLotusPricePrevious > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaLotusPricePrevious)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaLotusPricePrevious)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{
                                    numberWithCommas(talaLotusPricePrevious)
                                  }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>
                        </div>
                      </b-row>

                      <hr />

                      <b-row class="test1" dir="rtl">
                        <div>
                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <b style="font-size: 0.8em">
                                  <!-- <v-icon
                                    title="نمودار"
                                    class="ml-2"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="ml-1"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  صندوق پشتوانه طلای مفید (عیار)
                                </b>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaAyarPriceOpen > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaAyarPriceOpen)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaAyarPriceOpen)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>

                              <b-col cols="3">
                                <b>
                                  {{ numberWithCommas(talaAyarPriceOpen) }}
                                </b>
                              </b-col>
                            </b-row>
                            <br />
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به طلای خام سكه
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaAyarSeke > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(HobabTalaAyarSeke)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaAyarSeke)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaAyarSeke) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به NAV
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaAyarNav > 0">
                                  <b style="color: green">
                                    {{ numberWithCommas(HobabTalaAyarNav) }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaAyarNav)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaAyarNav) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  مقدار NAV ابطال
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaAyarPricePrevious > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaAyarPricePrevious)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaAyarPricePrevious)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{
                                    numberWithCommas(talaAyarPricePrevious)
                                  }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>
                        </div>
                      </b-row>
                      <hr />

                      <b-row class="test1" dir="rtl">
                        <div>
                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <b style="font-size: 0.8em">
                                  <!-- <v-icon
                                    title="نمودار"
                                    class="ml-2"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->
                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="ml-1"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  صندوق پشتوانه طلای زر (زر)
                                </b>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaZarPriceOpen > 0">
                                  <b style="color: green">
                                    {{ numberWithCommas(talaZarPriceOpen) }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaZarPriceOpen)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>

                              <b-col cols="3">
                                <b>
                                  {{ numberWithCommas(talaZarPriceOpen) }}
                                </b>
                              </b-col>
                            </b-row>
                            <br />
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به طلای خام سكه
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaZarSeke > 0">
                                  <b style="color: green">
                                    {{ numberWithCommas(HobabTalaZarSeke) }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaZarSeke)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaZarSeke) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به NAV
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaZarNav > 0">
                                  <b style="color: green">
                                    {{ numberWithCommas(HobabTalaZarNav) }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaZarNav)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaZarNav) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  مقدار NAV ابطال
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaZarPricePrevious > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaZarPricePrevious)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaZarPricePrevious)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{
                                    numberWithCommas(talaZarPricePrevious)
                                  }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>
                        </div>
                      </b-row>
                      <hr />

                      <b-row class="test1" dir="rtl">
                        <div>
                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <b style="font-size: 0.8em">
                                  <!-- <v-icon
                                    title="نمودار"
                                    class="ml-2"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="ml-1"
                                    style="font-size: 18px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  صندوق پشتوانه طلای کیان (گوهر)
                                </b>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaGoharPriceOpen > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaGoharPriceOpen)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaGoharPriceOpen)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>

                              <b-col cols="3">
                                <b>
                                  {{ numberWithCommas(talaGoharPriceOpen) }}
                                </b>
                              </b-col>
                            </b-row>
                            <br />
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->
                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به طلای خام سكه
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaGoharSeke > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(HobabTalaGoharSeke)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaGoharSeke)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaGoharSeke) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  حباب نسبت به NAV
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="HobabTalaGoharNav > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(HobabTalaGoharNav)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(HobabTalaGoharNav)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{ numberWithCommas(HobabTalaGoharNav) }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>

                          <div>
                            <b-row align="right">
                              <b-col class="pl-0" cols="6">
                                <div class="hob">
                                  <!-- <v-icon
                                    title="نمودار"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >show_chart</v-icon
                                  > -->

                                  <img
                                    class="img-responsive mt-0 mb-0 pt-0 pb-0"
                                    width="20px"
                                    height="20px"
                                    src="@/assets/chart.png"
                                    alt="طلاگرام"
                                    @click="showChart()"
                                    title="نمودار"
                                    style="cursor: pointer"
                                  />

                                  <v-icon
                                    title="اطلاعات"
                                    class="mr-1"
                                    style="font-size: 16px; color: #f5d438"
                                    @click="showChart()"
                                    >info</v-icon
                                  >

                                  مقدار NAV ابطال
                                </div>
                              </b-col>

                              <b-col class="pr-0" cols="3">
                                <div v-if="talaGoharPricePrevious > 0">
                                  <b style="color: green">
                                    {{
                                      numberWithCommas(talaGoharPricePrevious)
                                    }}%</b
                                  >
                                </div>
                                <div v-else>
                                  <b style="color: red">
                                    ({{
                                      numberWithCommas(talaGoharPricePrevious)
                                    }}%)</b
                                  >
                                </div>
                              </b-col>
                              <b-col cols="3">
                                <b style="color: rgb(99, 51, 51)">
                                  {{
                                    numberWithCommas(talaGoharPricePrevious)
                                  }}</b
                                >
                              </b-col>
                            </b-row>
                          </div>
                        </div>
                      </b-row>
                    </b-card-text>
                  </div>
                </b-card>
              </b-card-group>
            </b-col>
          </b-row>
        </b-col>

        <b-col cols="1"> </b-col>
      </b-row>

      <br /><br />

      <br /><br />

      <!-- <div class="chart" ref="chart1"></div> -->
    </div>
  </div>
</template>

<script>
import axios from "axios";
import config from "@/config";

// import { createChart } from "lightweight-charts";
//  import { LightweightCharts } from "lightweight-charts";

export default {
  name: "App",
  data() {
    return {
      url1: `${config.paseUrl}` + "api/v1/CurrentPrice/GetTalagram",
      // url2: `${config.paseUrl}` +"api/v1/ArchivedPrice/GetSekeByTimeFrame/?timeframe=5",

      //navbar
      isCollapseOpen: false,
      chart: null,
      chartData: [],
      // nerkhha
      dollar: 0,
      silver: 0,
      ons: 0,
      silverPrice: 0,
      mesghalPrice: 0,
      sekePrice: 0,
      sekeGhadimPrice: 0,
      HobabAbshode: 0,
      HobabSeke: 0,
      HobabSekeGhadim: 0,
      HobabNim: 0,
      HobabRob: 0,
      HobabGerami: 0,
      mesghalRiyal: 0,
      sekeRiyal: 0,
      geramTalaPrice: 0,
      gram24TalaPrice: 0,
      nimPrice: 0,
      robPrice: 0,
      sekeGeramiPrice: 0,
      sekeRefahPrice: 0,
      HobabRefahCoinFree: 0,
      HobabRefahCoinSekeRiyal: 0,
      sekeSaderatPrice: 0,
      HobabSaderatCoinFree: 0,
      HobabSaderatCoinSekeRiyal: 0,
      sekeMellatPrice: 0,
      HobabMellatCoinFree: 0,
      HobabMellatCoinSekeRiyal: 0,
      sekeSamanPrice: 0,
      HobabSamanCoinFree: 0,
      HobabSamanCoinSekeRiyal: 0,
      talaLotusPriceOpen: 0,
      HobabTalaLotusSeke: 0,
      HobabTalaLotusNav: 0,
      talaLotusPricePrevious: 0,
      talaAyarPriceOpen: 0,
      HobabTalaAyarSeke: 0,
      HobabTalaAyarNav: 0,
      talaAyarPricePrevious: 0,
      talaZarPriceOpen: 0,
      HobabTalaZarSeke: 0,
      HobabTalaZarNav: 0,
      talaZarPricePrevious: 0,
      talaGoharPriceOpen: 0,
      HobabTalaGoharSeke: 0,
      HobabTalaGoharNav: 0,
      talaGoharPricePrevious: 0,
      showHobabRefah: false,
      showHobabSaderat: false,
      showHobabMelat: false,
      showHobabSaman: false,
      showHobabLoutos: false,
      showHobabEyar: false,
      showHobabZar: false,
      showHobabGohar: false,
      showHobabmesghal: false,
      showHobabSeke: false,
      showHobabGhadim: false,
      showHobabNim: false,
      showHobabRob: false,
      showHobabGerami: false,
      //date
      today: 0,
    };
  },
  components: {},
  mounted() {},
  methods: {
    //chart
    showChart() {
      this.$router.push({ path: "/MainChart" });
    },

    //nrkhha
    showHobabRefahDetail() {
      this.showHobabRefah = !this.showHobabRefah;
    },
    showHobabSaderatDetail() {
      this.showHobabSaderat = !this.showHobabSaderat;
    },
    showHobabMelatDetail() {
      this.showHobabMelat = !this.showHobabMelat;
    },
    showHobabSamanDetail() {
      this.showHobabSaman = !this.showHobabSaman;
    },
    showHobabLoutosDetails() {
      this.showHobabLoutos = !this.showHobabLoutos;
    },
    showHobabEyarDetails() {
      this.showHobabEyar = !this.showHobabEyar;
    },
    showHobabZarDetails() {
      this.showHobabZar = !this.showHobabZar;
    },
    showHobabGoharDetails() {
      this.showHobabGohar = !this.showHobabGohar;
    },
    showHobabmesghalDetails() {
      this.showHobabmesghal = !this.showHobabmesghal;
    },
    showHobabSekeDetails() {
      this.showHobabSeke = !this.showHobabSeke;
    },
    showHobabGhadimDetails() {
      this.showHobabGhadim = !this.showHobabGhadim;
    },
    showHobabNimDetails() {
      this.showHobabNim = !this.showHobabNim;
    },
    showHobabRobDetails() {
      this.showHobabRob = !this.showHobabRob;
    },
    showHobabGeramiDetails() {
      this.showHobabGerami = !this.showHobabGerami;
    },
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
  async created() {
    //date
    this.today = new Date().toLocaleDateString("fa-IR");
    await axios

      .get(`http://localhost:8080/api/v1/CurrentPrice/GetTalagram`, {})

      // .get(this.url1, {
      // })
      .then((response) => {
        this.dollar = response.data.Data.usdPrice;
        this.ons = response.data.Data.onsPrice.toLocaleString();
        this.silver = response.data.Data.silverPrice;
        this.geramTalaPrice =
          response.data.Data.geramTalaPrice.toLocaleString();
        this.gram24TalaPrice =
          response.data.Data.gram24TalaPrice.toLocaleString();
        this.nimPrice = response.data.Data.nimPrice;
        this.robPrice = response.data.Data.robPrice;
        this.sekeGeramiPrice = response.data.Data.sekeGeramiPrice;
        this.sekeRefahPrice = response.data.Data.sekeRefahPrice;
        this.HobabRefahCoinFree = response.data.Data.HobabRefahCoinFree;
        this.HobabRefahCoinSekeRiyal =
          response.data.Data.HobabRefahCoinSekeRiyal;
        this.sekeSaderatPrice = response.data.Data.sekeSaderatPrice;
        this.HobabSaderatCoinFree = response.data.Data.HobabSaderatCoinFree;
        this.HobabSaderatCoinSekeRiyal =
          response.data.Data.HobabSaderatCoinSekeRiyal;
        this.sekeMellatPrice = response.data.Data.sekeMellatPrice;
        this.HobabMellatCoinFree = response.data.Data.HobabMellatCoinFree;
        this.HobabMellatCoinSekeRiyal =
          response.data.Data.HobabMellatCoinSekeRiyal;
        this.sekeSamanPrice = response.data.Data.sekeSamanPrice;
        this.HobabSamanCoinFree = response.data.Data.HobabSamanCoinFree;
        this.HobabSamanCoinSekeRiyal =
          response.data.Data.HobabSamanCoinSekeRiyal;
        this.talaLotusPriceOpen = response.data.Data.talaLotusPriceOpen;
        this.HobabTalaLotusSeke = response.data.Data.HobabTalaLotusSeke;
        this.HobabTalaLotusNav = response.data.Data.HobabTalaLotusNav;
        this.talaLotusPricePrevious = response.data.Data.talaLotusPricePrevious;
        this.talaAyarPriceOpen = response.data.Data.talaAyarPriceOpen;
        this.HobabTalaAyarSeke = response.data.Data.HobabTalaAyarSeke;
        this.HobabTalaAyarNav = response.data.Data.HobabTalaAyarNav;
        this.talaAyarPricePrevious = response.data.Data.talaAyarPricePrevious;
        this.talaZarPriceOpen = response.data.Data.talaZarPriceOpen;
        this.HobabTalaZarSeke = response.data.Data.HobabTalaZarSeke;
        this.HobabTalaZarNav = response.data.Data.HobabTalaZarNav;
        this.talaZarPricePrevious = response.data.Data.talaZarPricePrevious;
        this.talaGoharPriceOpen = response.data.Data.talaGoharPriceOpen;
        this.HobabTalaGoharSeke = response.data.Data.HobabTalaGoharSeke;
        this.HobabTalaGoharNav = response.data.Data.HobabTalaGoharNav;
        this.talaGoharPricePrevious = response.data.Data.talaGoharPricePrevious;
        this.silverPrice = response.data.Data.silverPrice;
        this.mesghalPrice = response.data.Data.mesghalPrice;
        this.sekePrice = response.data.Data.sekePrice;
        this.sekeGhadimPrice = response.data.Data.sekeGhadimPrice;
        this.HobabAbshode = response.data.Data.HobabAbshode;
        this.HobabSeke = response.data.Data.HobabSeke;
        this.HobabSekeGhadim = response.data.Data.HobabSekeGhadim;
        this.HobabNim = response.data.Data.HobabNim;
        this.HobabRob = response.data.Data.HobabRob;
        this.HobabGerami = response.data.Data.HobabGerami;
        this.sekeRiyal = response.data.Data.sekeRiyal.toLocaleString();
        this.mesghalRiyal = response.data.Data.mesghalRiyal.toLocaleString();
      })
      .catch((e) => {
        this.errors.push(e);
      });
  },
};
</script>

<style scope>
.chart {
  position: absolute;
  width: 100%;
  height: 300px;
}
.test {
  text-align: right !important;
  margin: 0 px;
  padding-bottom: 0% !important;
}
.test1 {
  margin-bottom: 0% !important;
}

p {
  padding: 0%;
  margin: 0%;
  margin-bottom: 0% !important;
}
.background {
  margin: 0.5% !important;
  padding: 0.3%;
  width: 11em;
  border-radius: 20px;
  border-style: solid;
  color: #0486a2;

  border-color: rgb(253, 250, 250);
}

.card-header {
  background-color: #0486a2;
}

div.card-header {
  border-top-left-radius: 19px !important;
  border-top-right-radius: 19px !important;
}
.hob {
  font-size: 0.8em;
  color: rgb(99, 51, 51);
}
.grid {
  margin-bottom: 1em;
}
</style>
