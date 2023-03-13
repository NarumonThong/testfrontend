<template>
  <v-app id="home">
    <NavBar />
    <v-container fluid >
      <v-col  cols="12" class="mt-12 ml-10" id="about">
        <div>
          <v-row class="mt-8">
            <v-col cols="12" sm="2"></v-col>

            <v-col cols="12" sm="3">
              <h4 class="hone mt-10">LOREM </h4>
              <h4 class="htwo">IPSUM</h4>
              <p class="done text-white">
                Lorem Ipsum is simply Lorem Ipsum is simply Lorem Ipsum is simply
              </p>
              <br />
              <p class="dtwo text-grey">
                Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's 
              </p>
            </v-col>

            <v-col cols="12" sm="5">
              <v-img src="bicycle.png" max-height="300" class="mt-16"></v-img>
            </v-col>

            <v-col cols="12" sm="2"></v-col>
            
          </v-row>
        </div>
      </v-col>

      <v-col cols="12" class="padd mt-12" id="portfolio">
        <div class="first" id="project">
          <v-row>
            <v-col cols="12">
              <div class="child">
                <h1 class="hthree text-white ml-3 mt-4">LOREM IPSUM LOREM</h1>
                <v-img src="ellipse.png" max-height="100" class="mt-16"></v-img>
                <h3 class="text-white ml-3 mt-4">Lorem Ipsum is simply</h3>
                <p class="text-grey ml-3 mt-4 text-caption">
                  Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has <br />been the industry's standard dummy text ever since the 1500s, when an unknown printer took
                  <br /> a galley of type and scrambled it to make a type specimen book. 
                </p>
              </div>
            </v-col>
          </v-row>
        </div>
      </v-col>
      
      <v-col cols="12"  id="page">
        <div class="pre" >
          <v-col cols="12" sm="12">
              <h1 class="mt-9">LOREM IPSUM</h1>
          </v-col>
          <div class="mt-16">
            <v-row >
              <v-col v-for="item in products" :key="item.id" >
                <v-card class="mx-auto" max-width="304" height="360">
                  <v-img src="rectangle.png" height="200px" cover></v-img>

                  <v-card-title>{{ item.title }}</v-card-title>

                  <v-card-subtitle>
                    {{item.title}}
                  </v-card-subtitle>
                  <v-card-text>
                    {{item.description}}
                  </v-card-text>
                </v-card>
              </v-col>
            </v-row>
          </div>
          
        </div>
      </v-col>

      
      <v-col cols="12" sm="12" class="px-16" id="contact">
        <v-row>
          <v-col cols="12" sm="7">
            <v-img src="bicycle.png" max-height="300" class="mt-16"></v-img>
          </v-col>
          <v-col cols="12" sm="4">
            <h1 class="mt-8 text-white">ติดต่อเรา</h1>
            <v-container>
              <v-text-field
                color="primary"
                label="ชื่อ - นามสกุล"
                variant="underlined"
              ></v-text-field>

              <v-text-field
                color="primary"
                label="เบอร์ติดต่อ"
                variant="underlined"
              ></v-text-field>

              <v-text-field
                color="primary"
                label="อีเมล"
                variant="underlined"
              ></v-text-field>

              

              <v-text-field 
                label="วันที่"
                type="date"
                variant="underlined"
              ></v-text-field>

              

            </v-container>

            
            <p class="fo text-white">
                Lorem Ipsum is simply dummy text
            </p>
            <p class="fo text-white">
                Lorem Ipsum is simply dummy te
            </p>

            <v-btn color="#DEE34B" class="mt-16 mb-16">LOREM</v-btn>
          </v-col>
          <v-col cols="12" sm="1">
          </v-col>
        </v-row>
      </v-col>

    </v-container>
    <!-- <FooterView /> -->
  </v-app>
</template>

<script>
import { defineComponent } from "vue";
import NavBar from "../components/NavBar.vue";
import axios from 'axios'

export default defineComponent({
  name: "HomeView",
  data() {
    return {
      products: []
    }
  },
  components: {
    NavBar
  },
  mounted() {
    let vm = this;
    axios.get('https://dummyjson.com/products?limit=3')
    .then(function(res){
      vm.products = res.data.products
      // console.log(res.data.products)
    })
  }
});
</script>

<style scoped>

.v-container {
  background: rgb(0, 0, 0);
  padding: 16px 0 16px 0;
}
.v-text-field {
  color: #ffff;
}
.fo {
  color: #ffff;
  font-size: 12px;
}

.head {
  position: relative;
  text-align: center;
  padding: 12px;
  margin-bottom: 6px;
  height: 400px;
  width: 100%;
  color: white;
}
.head:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 50%;
  background: black;
  transform: skew(0deg, 6deg);
}
.head:after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 50%;
  background: black;
  transform: skew(0deg, -6deg);
}
.first {
  width: 100%;
  height: 480px;
  text-align: center;
  padding: 2rem 2rem;
}
.two {
  width: 100%;
  height: 480px;
  text-align: center;
  padding: 0 200px;
  background-color: #D9EF0C;
}
.child {
  display: inline-block;
  padding: 2rem 1rem;
  vertical-align: middle;
  text-align: center;
  margin-right: 8px;
}
.imgHover {
  padding: 0 200px;
}
.pre {
  width: 100%;
  height: 650px;
  text-align: center;
  padding: 0 200px;
  background-color: #D9EF0C;
;
}
.hone {
  font-weight: bold;
  font-size: 60px;
  color: #ffff;
  font-family: 'Montserrat';
}
.htwo {
  font-weight: bold;
  font-size: 60px;
  color: #D9EF0C;
  font-family: 'Montserrat';
}
.done{
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 24px;
  color: #ffff;
}
.dtwo {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 150%;
}
.hthree {
  font-weight: bold;
  font-size: 40px;
  color: #ffff;
  font-family: 'Montserrat';
}

</style>
