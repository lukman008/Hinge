<template>
    <div style="margin-top: -64px">
        <!-- <div class="dummy-bg--wrapper" :style="{ 'background-image': `url(${bg}`}"></div> -->
		<v-layout style="position: relative" :style="{ 'background-image': `url(${bg}`}" row wrap tag="section">
			<v-carousel style="height:100vh;"  hide-controls hide-delimiters class="elevation-0">
				<v-carousel-item
					v-for="(item,i) in taglines"
					:key="i"
					style=""
					class=" pt-5"
				>
					<v-layout fill-height justify-center align-center row wrap pt-5>
						<div class="text-xs-center pa-5">
							<h3  class="full-width white--text text-xs-center white-text display-3 font-weight-boldx mb-2">{{item.title}}</h3>
							<p class="title white--text">{{item.subheading}}</p>
						</div>
					</v-layout>
				</v-carousel-item>
			</v-carousel>
			<v-layout row wrap align-center justify-center style="position: absolute; left: 0; right: 0; bottom: 0;" py-3>
				<v-btn light small color="accent" fab @click="$vuetify.goTo($refs['what-we-do'], { duration: 300, easing: 'easeOutQuad' })">
					<v-icon color="black">mdi-chevron-double-down</v-icon>
				</v-btn>
			</v-layout>
		</v-layout>
		<v-layout row wrap tag="section" ref="what-we-do">
			<v-container grid-list-md>
				<v-layout row wrap>
					<v-flex xs12>
						<h2 class="display-1 font-weight-bold text-uppercase text-xs-center my-3">What we do</h2>
					</v-flex>
  <v-flex xs12 v-if="a1">
     <v-slide-x-transition >
       <v-layout row wrap>
         <v-flex xs12 md4 v-for="(item, i) in services" style="padding:5px;text-align:center"
      :key="i">
        <v-card class="elevation-0" color="transparent" height="400;"  >
          <v-card-title  class="title">{{item.title}}</v-card-title>
          <v-card-media>
            <v-icon size="72">{{item.icon}}</v-icon>
          </v-card-media>
          <v-card-text >
            <p>{{item.text}}</p>
          </v-card-text>
      </v-card>
      </v-flex>
       </v-layout>
      <!-- <v-timeline align-top>
    <v-timeline-item
      v-for="(item, i) in services"
      :key="i"
      :icon="item.icon"
      fill-dot
    >
      <v-card
        
      >
        <v-card-title class="title">{{item.title}}</v-card-title>
        <v-card-text >
          <p>{{item.text}}</p>
        </v-card-text>
      </v-card>
    </v-timeline-item>
  </v-timeline> -->
     </v-slide-x-transition>
  </v-flex>
  
				</v-layout>
			</v-container>
		</v-layout>
		<v-layout v-show="a2" row wrap>
			<v-container grid-list-md>
				<v-layout row wrap>
					<v-flex xs12>
						<h2 class="display-1 font-weight-bold text-uppercase text-xs-center my-3">AFFLIATED INDUSTRIES</h2>
					</v-flex>
					<v-flex v-for="i in sectors" :key="i.title" xs12 sm6 md4 style="padding: 20px;">
						<v-card color="transparent" style="min-height:30vh">
							<v-card-title class="title" >
								<h5 class="headline text-xs-center d-block mx-auto">{{i.title}}</h5>
							</v-card-title>
							<v-img
								:src="i.icon"
								aspect-ratio="2.5"
                contain
							>
								<v-layout
									slot="placeholder"
									fill-height
									align-center
									justify-center
									ma-0
								>
									<v-progress-circular indeterminate color="accent"></v-progress-circular>
								</v-layout>
							</v-img>
							<!-- <v-card-actions>
								<v-btn color="primary" class="d-block mx-auto">Read more</v-btn>
							</v-card-actions> -->
						</v-card>
					</v-flex>
				</v-layout>
			</v-container>
		</v-layout>

		<v-layout v-show="a3" row wrap tag="section">
			<v-container grid-list-md>
				<v-layout row wrap justify-center align-center style="height: 600px">
					<v-flex xs12>
						<v-layout row wrap py-5 class="showcase-item--wrapper">
							<v-flex xs12>
								<h2 class="display-1 font-weight-bold text-uppercase text-xs-center my-3">PROUD CLIENTS</h2>
							</v-flex>
							<v-flex v-for="(item, index) in clients" :key="index" xs6 md3 class="my-3">
								<v-layout justify-center align-center column wrap class="showcase-item">
									<v-img min-height="64px" min-width="64px"  :src="item.logo" aspect-ratio="2.5"
                contain class="mb-2"/>
									<div class="text-xs-center">
										<h6 class="text-uppercase font-weight-light headline body-2">{{ item.name }}</h6>
									</div>
								</v-layout>
							</v-flex>
						</v-layout>
					</v-flex>
				</v-layout>
			</v-container>
		</v-layout>
		<v-layout v-show="a4" row wrap tag="section">
			<v-flex xs12>
				<v-parallax
					
					:src="parallax"
				>
					<v-layout
						align-center
						column
						justify-center
					>
						<h3 class="display-2 font-weight-thin mb-3">Work with us today</h3>
						<v-btn href="mailto:e.odunlade@devsdistrictnigeria.com?subject=Hinge Systems Inquiry" depressed large color="red lighten-1 white--text">GET QUOTE</v-btn>
					</v-layout>
				</v-parallax>
			</v-flex>
		</v-layout>
   <v-footer
    
    height="auto"
  >
    <v-card
      class="flex"
      flat
      tile
    >
      <v-card-title class="en-4">
        <strong class="subheading">Connect with us!</strong>

        <v-spacer></v-spacer>

        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-3"
          href="#"
          
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-title>

      <v-card-actions class="grey lighten-3 en-3 justify-center">
        &copy;2019 — <strong>Hinge Systems</strong>
      </v-card-actions>
    </v-card>
  </v-footer>
    </div>
</template>

<script>
import bg from "@/assets/1.jpg";
import pg from "@/assets/1.jpg";
import img from "@/assets/1.jpg";
import augma from "@/assets/2.jpg";
import img2 from "@/assets/1.jpg";
import parallax from "@/assets/3.jpg";
import _data from "@/assets/data.svg";
import _estate from "@/assets/estate.svg";
import _medicine from "@/assets/medicine.svg";
import _military from "@/assets/military.svg";
import _aviation from "@/assets/aviation.svg";
import _comm from "@/assets/comms.svg";
import aircom from "@/assets/aircom.png";
import mantis from "@/assets/mantis.jpg";
import zenith from "@/assets/zenith.png";
export default {
  mounted() {
    setTimeout(() => {
      this.a1 = true;
    }, 200);
    setTimeout(() => {
      this.a2 = true;
    }, 400);
    setTimeout(() => {
      this.a3 = true;
    }, 600);
    setTimeout(() => {
      this.a4 = true;
    }, 800);
  },
  data() {
    return {
      bg,
      pg,
      img,
      augma,
      img2,
      parallax,
      a1: false,
      a2: false,
      a3: false,
      a4: false,
      icons: [
        "mdi-facebook",
        "mdi-twitter",
        "mdi-google-plus",
        "mdi-linkedin",
        "mdi-instagram"
      ],
      services: [
         {
          title: "IoT Product Design and Developments",
          icon: "mdi-image-filter-tilt-shift",
          text:
            "We understand your need to develop new IoT devices. Our team diverse team of engineers work with you from Idea conceptualization and user research to Design, Rapid prototyping and micro manufacturing. We also connect you with manufacturers within our network for high volume manufacturing"
        },
        {
          title: "Consulting / Systems and Service Design",
          icon: "mdi-information-outline",
          text:
            "IoT offers an opportunity for real-time monitoring, process automation and so much, all of which could be key drivers to take your business to the next level. we sit down with you with a deep understanding of the fact that no two use cases are the same and carefully analyze your use case and develop a custom IoT Solution/Strategy, tailor-made to help you achieve your goals. We identify all the system components and help you select the best based on functionality and cost."
        },
       
        {
          title: "Smart Systems and Services Design",
          icon: "mdi-satellite-variant",
          text:
            "We believe smart systems design needs to transcend just making existing products or services more attractive and extend the experiences that users will have with connected systems by better integrating the processes that are behind these experiences with design and technological decisions"
        }
      ],
      clients: [
        {
          name: "Zenith Bank PLC",
          logo: zenith
        },
        {
          name: "Mantis FM",
          logo: mantis
        },
        {
          name: "AirCom NG",
          logo: aircom
        },
        {
          name: "Isoceles",
          logo: zenith
        }
      ],
      sectors: [
        {
          title: "Utility automation",
          icon: _estate
        },
        {
          title: "Medicine",
          icon: _medicine
        },
        {
          title: "Military",
          icon: _military
        },
        {
          title: "Aviation",
          icon: _aviation
        },
        {
          title: "Big Data",
          icon: _data
        },
        {
          title: "Telecommunication",
          icon: _comm
        }
      ],
      taglines: [
        {
          title: "Custom IoT Solutions for your best work",
          subheading:
            "Leverage on the power of IoT for growth and improved efficiency"
        },
        {
          title:
            "Hardware Fabrication from prototype to battle-tested solutions",
          subheading:
            "Boost your industry's productivity 10x with custom IoT devices"
        },
        {
          title: " IoT Consulting service for all industries ",
          subheading: "Think it, We'll make it."
        }
      ],
      showcaseItems: [
        { name: "Schools Visited", value: "87", icon: "mdi-school" },
        { name: "Kids Trained", value: "5 K", icon: "mdi-human-male-female" },
        { name: "ICT Labs Equiped", value: "5", icon: "mdi-bank" },
        { name: "Proud Volunteers", value: "25", icon: "mdi-emoticon" }
        // for design purposes, keep this has 4
      ]
    };
  }
};
</script>

<style>
.dummy-bg--wrapper {
  height: 100vh;
  widows: 100vw;
  position: absolute;
  top: 0;
  right: 0;
  left: 0;
  background-position: center top;
  background-size: cover;
}
.showcase-item--wrapper {
  box-shadow: 0 24px 35px rgba(0, 0, 0, 0.06);
  background-color: rgba(250, 248, 248, 0.89);
  background-attachment: fixed;
  min-width: 200px;
}
.showcase-item--wrapper .showcase-item h5 {
  letter-spacing: 1px;
}
</style>