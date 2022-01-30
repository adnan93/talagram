<template>
  <div class="backGround">
    <b-row dir="rtl">
      <b-col cols="2"> </b-col>
      <b-col cols="8">

        <b-row class="mt-2" align="center">
          <b-col>
            <div>
              <img
                src="../assets/meskal.jpg"
                width="250 em"
                height="50%"
                style="border-radius: 18px"
              />
            </div>
          </b-col>
        </b-row>


        <b-row class="mt-2" align="center">
          <b-col>
            <div class="">
              <b style="color: #d9b34a; font-size: 25px"> سکه زمزد </b>
              <br />
            </div>
          </b-col>
        </b-row>
        

        <b-row class="mt-2" align="center">
          <b-col >
            <div class="card3">
              <p>
                {{ today }}
                <br />
                {{ time }}
              </p>
            </div>
          </b-col>

          <b-col>
            <div class="card3">
              <h6>
                <a style="text-decoration: none" href="tel:07132301858">
                  <p style="color: #742b6c">071-32301858</p>
                </a>

                <a style="text-decoration: none" href="tel:09171092419">
                  <p style="color: #742b6c; font-size: 18px">09171092419</p>
                </a>
              </h6>
            </div>
          </b-col>
        </b-row>

        <br />
        <b-row align="center">
          <b-col>
            <div class="card2">
              <b style="font-size: 15px"> یک مثقال طلای 17 عیار</b>
              <b> {{ mesghalPrice }} </b>
            </div>
          </b-col>

          <b-col>
            <div class="card2">
              <b-row>
                <b style="font-size: 16px"> یک گرم طلای 18 عیار </b></b-row
              >
              <b-row>
                <b>
                  {{ geramTalaPrice }}
                </b></b-row
              >
            </div>
          </b-col>
        </b-row>
        <br />
        <b-row align="center">
          <b-col
            ><div class="card1">
              <b> تمام سکه 86 </b>
              {{ sekePrice }}
            </div>
          </b-col>
          <b-col>
            <div class="card1">
              <b style="font-size: 14px"> سکه یک گرمی </b>

              {{ sekeGeramiPrice }}
            </div>
          </b-col>
        </b-row>
        <br />
        <b-row align="center">
          <b-col
            ><div class="card1">
              <b> نیم سکه 68 </b>
              {{ nimPrice }}
            </div>
          </b-col>
          <b-col
            ><div class="card1">
              <b style="font-size: 14px"> انس جهانی طلا </b>

              {{ ons }}
            </div>
          </b-col>
        </b-row>
        <br />
        <b-row align="center">
          <b-col>
            <div class="card1">
              <b style="font-size: 13px"> ربع سکه 86</b>
              {{ robPrice }}
            </div>
          </b-col>

          <b-col>
            <div class="card1">
              <b-row>
                <b> دلار </b>
              </b-row>

              {{ usdPrice }}
            </div>
          </b-col>
        </b-row>

        <div class="mt-2">
          <p
            align="center"
            class="mt-4"
            style="color: #d9b34a; font-size: 15px"
          >
            شیراز، خیابان قصرالدشت، چهارراه ملاصدرا، مرکز خرید طلا و جواهر پارس،
            طبقه همکف واحد 29
          </p>
        </div>

  

        <br />
      </b-col>

      <b-col cols="2"> </b-col>
    </b-row>

  </div>
</template>

<script>
import axios from "axios";
import config from "@/config";
export default {
  data() {
    return {
      list: [],
      timer: "",

      url1: `${config.paseUrl}` + "api/v1/CurrentPrice/GetTalagram",

      //Date
      today: 0,
      time: 0,

      //nerhkha
      dollar: 0,
      ons: 0,
      sekePrice: 0,
      mesghalPrice: 0,
      sekeGhadimPrice: 0,
      sekeRiyal: 0,
      geramTalaPrice: 0,
      gram24TalaPrice: 0,
      nimPrice: 0,
      robPrice: 0,
      sekeGeramiPrice: 0,
      usdPrice: 0,
    };
  },

  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },

  async mounted() {
    //Date
    this.today = new Date().toLocaleDateString("fa-IR");
    this.time = new Date(new Date().getTime()).toLocaleTimeString("en-GB");

    await axios
      .get(`http://localhost:8080/api/v1/CurrentPrice/GetTalagram`, {})

      // await axios
      //   .get(this.url1, {

      //   })
      .then((response) => {
        this.dollar = response.data.Data.usdPrice;
        this.ons = response.data.Data.onsPrice.toLocaleString();
        this.silver = response.data.Data.silverPrice.toLocaleString();
        this.geramTalaPrice =
          response.data.Data.geramTalaPrice.toLocaleString();
        this.gram24TalaPrice =
          response.data.Data.gram24TalaPrice.toLocaleString();
        this.nimPrice = this.numberWithCommas(response.data.Data.nimPrice);
        this.robPrice = this.numberWithCommas(response.data.Data.robPrice);
        this.sekeGeramiPrice = this.numberWithCommas(
          response.data.Data.sekeGeramiPrice
        );
        this.talaAyarPriceOpen = response.data.Data.talaAyarPriceOpen;

        this.sekePrice = response.data.Data.sekePrice.toLocaleString();
        this.mesghalRiyal = response.data.Data.mesghalRiyal.toLocaleString();
        this.usdPrice = response.data.Data.usdPrice.toLocaleString();
        this.mesghalPrice = response.data.Data.mesghalPrice.toLocaleString();
      })
      .catch((e) => {
        this.errors.push(e);
      });
  },
};
</script>

<style>
.card1 {
  background-color: #e3e3e0;
  border-radius: 18px;
  color: #742b6c;
  padding: 0.3em;
  box-shadow: 3px 5px 10px black;

}

.card2 {
  border-radius: 18px;
  color: cornsilk;
  height: 5em;
  background-color: #742b6c;
  box-shadow: 3px 5px 10px black;
  padding: 0.2em;

}

.card3 {
  border-radius: 18px;
  color: rgb(3, 3, 3);
  height: 4em;
  background-color: #e3e3e0;
  box-shadow: 3px 5px 10px black;
  padding: 0.3em;

}
.backGround {
  background-color: #ffffff;
}
</style>