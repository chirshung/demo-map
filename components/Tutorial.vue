<template>
  <main>
    <div class="wrapper">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h2 id="lines">Rail Lines</h2>
          </div>
        </div>
        <div class="row">
          <div class="col-xs-12">
            <h3 id="mrt">MRT Lines</h3>
          </div>
          <div class="col-xs-12 col-md-6 network-list">
            <a href="https://www.sgtrains.com/network-nsl.html">
              <div class="network-overlay nsl">
                <div class="line line-mrt nsl">North-South Line</div>
                <p class="network-dest"><span class="stn"><span class="destcode nsl">4</span> <span class="stncode nsl">NS1</span> Jurong East</span> | <span class="stn"><span class="destcode nsl">5</span> <span class="stn"><span class="stncode nsl">NS28</span> Marina South Pier</span></span></p>
                <p>
                  High capacity line with
                  27 stations over 45km
                </p>
              </div>
            </a>
          </div>
          <div class="col-xs-12 col-md-6 network-list">
            <a href="https://www.sgtrains.com/network-ewl.html">
              <div class="network-overlay ewl">
                <div class="line line-mrt ewl">East-West Line</div>
                <p class="network-dest"><span class="stn"><span class="destcode ewl">1</span> <span class="stncode ewl">EW1</span> Pasir Ris</span> | <span class="stn"><span class="destcode ewl">2</span> <span class="stn"><span class="stncode ewl">EW33</span> Tuas Link</span></span> | <span class="stn"><span class="destcode ewl">3</span> <span class="stn"><span class="stncode ewl">CG2</span> Changi Airport</span></span></p>
                <p>
                  High capacity line with 35 stations over 56.7km 
                </p>
              </div>
            </a>
          </div>
          <div class="col-xs-12 col-md-6 network-list">
            <a href="https://www.sgtrains.com/network-nel.html">
              <div class="network-overlay nel">
                <div class="line line-mrt nel">North East Line</div>
                <p class="network-dest"><span class="stn"><span class="destcode nel">6</span> <span class="stncode nel">NE1</span> HarbourFront</span> | <span class="stn"><span class="destcode nel">7</span> <span class="stn"><span class="stncode nel">NE17</span> Punggol</span></span></p>
                <p>
                  Automated high capacity line with
                  16 stations over 20km 
                </p>
              </div>
            </a>
          </div>
          
        </div>
        
        
        
      </div>
    </div>

    <div class="map">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <div class="clear-margin-bottom">
              <h2 id="map">Future Train Network Map</h2>
            </div>
          </div>
        </div>
      </div>
        
      <div id="systemmap" class="pointer-only leaflet-container leaflet-touch leaflet-fade-anim leaflet-grab leaflet-touch-drag leaflet-touch-zoom" tabindex="0" style="position: relative;"><div class="leaflet-pane leaflet-map-pane" style="transform: translate3d(0px, -190px, 0px);"><div class="leaflet-pane leaflet-tile-pane"></div><div class="leaflet-pane leaflet-shadow-pane"></div><div class="leaflet-pane leaflet-overlay-pane"><object class="leaflet-image-layer leaflet-zoom-animated" data="./Network _ SGTrains.com_files/systemmap_2021.svg" style="z-index: 1; transform: translate3d(377px, 40px, 0px); width: 594px; height: 420px;"></object></div><div class="leaflet-pane leaflet-marker-pane"></div><div class="leaflet-pane leaflet-tooltip-pane"></div><div class="leaflet-pane leaflet-popup-pane"></div><div class="leaflet-proxy leaflet-zoom-animated" style="transform: translate3d(297.5px, -210px, 0px) scale(1);"></div></div><div class="leaflet-control-container"><div class="leaflet-top leaflet-left"><div class="leaflet-control-zoom leaflet-bar leaflet-control"><a class="leaflet-control-zoom-in" href="https://www.sgtrains.com/network.html#" title="Zoom in" role="button" aria-label="Zoom in">+</a><a class="leaflet-control-zoom-out" href="https://www.sgtrains.com/network.html#" title="Zoom out" role="button" aria-label="Zoom out">&#8722;</a></div></div><div class="leaflet-top leaflet-right"></div><div class="leaflet-bottom leaflet-left"></div><div class="leaflet-bottom leaflet-right"></div></div></div>
        
      <!-- <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <object data="./Network _ SGTrains.com_files/systemmap_2021.svg" class="touch-only">Future Train Network Map</object>
            <p style="text-align: right;">Download: <a href="https://www.sgtrains.com/img/network/systemmap_2021.png" target="_blank">PNG</a> (for mobile) | <a href="https://www.sgtrains.com/img/network/systemmap_2021.pdf" target="_blank">PDF</a> (for print)</p>
          </div>
        </div>
      </div> -->
    </div>
  </main>
</template>

<script>
export default {
    mounted() {
        var map = L.map('systemmap', {
          crs: L.CRS.Simple,
          minZoom: 0,
          maxZoom: 4,
          zoomSnap: 0.5,
          zoomDelta: 0.5,
          wheelPxPerZoomLevel: 100,
          attributionControl: false
        });
        var bounds = [[0,0], [210,297]];
        var image = L.imageOverlay('../../assets/img/systemmap_2021.svg', bounds, {alt: 'Singapore Train Network Map'}).addTo(map);
        map.fitBounds([[10,10], [200,287]]);
        map.setMaxBounds([[-10,-10], [220,307]]);
    },
    head: {   		
      link: [                  
        // { rel: 'stylesheet', href: './Network _ SGTrains.com_files/leaflet.css'},  
      ],			
      script: [  
        {        
            src: "https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js",
            type: "text/javascript",
            body: true //set this 'script' before the </body>        
        },
        {        
            src: "/assets/js/respond.min.js",
            type: "text/javascript",		  
            body: true //set this 'script' before the </body>        
        },
        // {        
        //     async: "",
        //     src: "./Network _ SGTrains.com_files/analytics.js.t&#7843;i xu&#7889;ng",
        //     type: "text/javascript",		  
        // },
        // {        
        //     src: "./Network _ SGTrains.com_files/leaflet.js.t&#7843;i xu&#7889;ng",
        //     type: "text/javascript",		  
        // },
        // {        
        //     src: "./Network _ SGTrains.com_files/jquery.min.js.t&#7843;i xu&#7889;ng",
        //     type: "text/javascript",		  
        // },
        // {        
        //     src: "./Network _ SGTrains.com_files/respond.min.js.t&#7843;i xu&#7889;ng",
        //     type: "text/javascript",		  
        // },
              
                   
      ]
    },

}
</script>

<style>
/* @import url("@/assets/css/mrt.css"); */
/* @import url("@/assets/css/leaflet.css"); */
/* @import url("@/assets/css/stylesheet.css"); */

.network-list{
  margin-bottom:24px;
  font-size:12px;
}
.network-list a{
  color:#FFF;
}
.network-list a:hover{
  position: relative;
  top: 2px;
  left: 2px;
}
.network-list img{
  width:100%;
  height:150px;
}
.network-dest{
  margin-bottom: 4px;
  font-size: 14px;
}

.line{
  min-width:150px;
  font-size:12px;
  padding-left:16px;
  margin-bottom:4px;
}
.network-overlay{
  padding:8px;
  min-height:90px;
  background-position:center center;
}
.network-overlay .line{
  display: block;
  width: 100%;
  font-size: 22px;
  padding-left: 42px;
  text-align: left;
  font-weight: normal;
}
.network-overlay p{
  margin-bottom: 2px;
}

.guide-list{
  margin-top:24px;
  margin-bottom:24px;
  font-size:12px;
}
.guide-list a{
  color:#FFF;
}
.guide-list a:hover{
  position: relative;
  top: 2px;
  left: 2px;
}
.guide-overlay{
  display: block;
  padding:2px 8px 12px 90px;
  width: 100%;
  min-height:82px;
  color: black;
  text-align: left;
  font-weight: normal;
  background-position:left center;
  background-repeat: no-repeat;
  background-color: white;
  background-size: 82px;
}
.guide-overlay p{
  margin-bottom: 2px;
}

.lines{
  background-image: url(/assets/img/network-lines.svg);
}
.networkmap{
  background-image: url(/assets/img/network-map.svg);
}
.history{
  background-image: url(/assets/img/network-history.svg);
}
.figures{
  background-image: url(/assets/img/network-figures.svg);
}

.row-scroll{
  overflow-x: scroll;
  white-space: nowrap;
  padding: 0 16px;
  margin: 16px 0 -32px 0;
  margin-bottom: 0px;
}
.year{
  vertical-align: top;
  text-align: center;
  display: inline-block;
  font-size: 32px;
  font-weight: lighter;
  width:200px;
  white-space: normal;
  margin-right: 16px;
  margin-top: 48px;
}
.year small{
  font-size: 16px;
  font-weight: normal;
}
.event{
  /*float: left;*/
  vertical-align: top;
  text-align: center;
  display: inline-block;
  font-size: 13px;
  line-height: 150%;
  width:200px;
  white-space: normal;
  margin-right: 16px;
}
.event .lead{
  margin: 12px;
  font-size: 18px;
  font-weight: lighter;
}

.map{
  color: #000;
  background-color: #ddd;
}
.unopened{
  opacity: 0.5;
}

#systemmap{
  height: 80vh;
}



@media (hover: none) {
  .pointer-only {
    display: none;
  }
}

@media (hover: hover) {
  .touch-only {
    display: none;
  }
}
</style>