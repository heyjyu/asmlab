---
geekdocHead: false
geekdocNav: false
geekdocAlign: left
geekdocAnchor: false
geekdocEditPath: false
geekdocFilePath:
geekdocRepo: 
geekdocBreadcrumb: false
geekdocHidden: true
---
<html itemscope itemtype="http://schema.org/Map" prefix="og: http://ogp.me/ns# fb: http://ogp.me/ns/fb#">
  <head>
      <meta charset="utf-8"/>
      <title>Model Result</title>
      <meta itemprop="name"                                      content="earth"/>
      <meta itemprop="description"     name="description"        content="model result"/>
      <meta property="og:type"        content="website"/>
      <meta property="og:title"       content="earth"/>
      <meta property="og:description" content="Model result of ASML"/>
      <meta property="og:url"         content="https://airsea.yonsei.ac.kr/model/"/>
      <meta property="og:image"       content="https://airsea.yonsei.ac.kr/images/banner.png"/>
      <link rel="shortcut icon" href="/favicon/asmllogo.svg"/>
      <link rel="apple-touch-icon" sizes="120x120" href="/favicon/asmllogo.svg"/>
      <link rel="apple-touch-icon" sizes="152x152" href="/favicon/asmllogo.svg"/>
      <link rel="stylesheet" type="text/css" href="/styles.css"/>
      <link rel="alternate" hreflang="x-default" href="https://airsea.yonsei.ac.kr/model/"/>
  </head>
  <body data-lang="en">
      <!--[if lte IE 8]><p id="warn">This site requires IE9 or newer.</p><![endif]-->
      <div id="display">
          <svg id="map" class="fill-screen" xmlns="http://www.w3.org/2000/svg" version="1.1"></svg>
          <canvas id="animation" class="fill-screen"></canvas>
          <canvas id="overlay" class="fill-screen"></canvas>
          <svg id="foreground" class="fill-screen" xmlns="http://www.w3.org/2000/svg" version="1.1"></svg>
      </div>
      <div id="sponsor" class="invisible">
          <p><span id="sponsor-hide" class="text-button invisible"> ✕ </span>community</p>
          <a id="sponsor-link" href="https://www.facebook.com/EarthWindMap">EarthWindMap</a>
      </div>
      <div id="details">
          <p id="status"></p>
          <div id="location">
              <p>
                  <span id="location-coord"></span>
                  <span id="location-close" class="invisible text-button"> ✕ </span>
              </p>
              <p>
                  <span id="location-wind"></span>
                  <span id="location-wind-units" class="text-button"></span>
              </p>
              <p>
                  <span id="location-value"></span>
                  <span id="location-value-units" class="text-button"></span>
              </p>
          </div>
          <p id="earth">
              <span id="show-menu" class="text-button" title="menu">≡</span>
              <span id="progress" class="invisible"></span>
          </p>
          <div id="menu" class="invisible">
              <p>Date | <span
                  id="data-date" class="local"></span> <span
                  id="toggle-zone" class="text-button"></span>
              </p>
              <p>Data | <span id="data-layer"></span></p>
              <p><span id="scale-label">Scale | </span><canvas id="scale"></canvas></p>
              <p>Source | <span id="data-center"></span></p>
              <p>Control | <span
                  class="text-button" id="nav-now" title="Current Conditions">Reset</span><span
                  class="text-button" id="nav-backward-more"> « </span> – <span
                  class="text-button" id="nav-backward"> ‹ </span> – <span
                  class="text-button" id="nav-forward"> › </span> – <span
                  class="text-button" id="nav-forward-more"> » </span><span
                  class="text-button" id="show-location" title="Current Position">〖◯〗</span>
              </p>
              <p>Mode | <span
                  class="text-button" id="ocean-mode-enable">Ocean</span> – <span
                  class="text-button" id="wind-mode-enable">Air</span>
              </p>
              <p class="ocean-mode">Simulation | <span
                class="model text-button" id="model-ESEA">ESEA</span> – <span
                class="model text-button" id="model-NWPac">NWPac</span> simulation
              </p>
              <p class="ocean-mode" id="depth">Depth | <span
                class="surface text-button" id="surface-level" title="Surface">Sfc</span> – <span
                class="surface text-button" id="depth-10m">10</span> – <span
                class="surface text-button" id="depth-30m">30</span> – <span
                class="surface text-button" id="depth-50m">50</span> – <span
                class="surface text-button" id="depth-100m">100</span> – <span
                class="surface text-button" id="depth-200m">200</span> – <span
                class="surface text-button" id="depth-300m">300</span> – <span
                class="surface text-button" id="depth-500m">500</span> – <span
                class="surface text-button" id="depth-700m">700</span> – <span
                class="surface text-button" id="depth-1000m">1000</span> – <span
                class="surface text-button" id="depth-1500m">1500</span> – <span
                class="surface text-button" id="depth-2000m">2000</span> – <span
                class="surface text-button" id="depth-3000m">3000</span> – <span
                class="surface text-button" id="depth-4000m">4000</span> m
            </p>
              <p class="ocean-mode">Overlay | <span
                  class="text-button" id="overlay-off">None</span> – <span
                  class="text-button" id="overlay-currents" title="Currents">Currents</span> – <span
                  class="text-button" id="overlay-temp" title="Temperature">Temp</span> – <span
                  class="text-button" id="overlay-salt" title="Salinity">Salt</span> – <span
                  class="text-button" id="overlay-SSH" title="SSH">SSH</span>
              </p>
              <!-- <p class="wind-mode"><span style="visibility:hidden">Overlay</span> | <span
                  class="text-button" id="overlay-total_precipitable_water" title="Total Precipitable Water">TPW</span> – <span
                  class="text-button" id="overlay-total_cloud_water" title="Total Cloud Water">TCW</span> – <span
                  class="text-button" id="overlay-mean_sea_level_pressure" title="Mean Sea Level Pressure">MSLP</span>
              </p> -->
              <p class="wind-mode invisible">Model | <span
                class="model text-button" id="model-SKRIPS">SKRIPS</span> model
              </p>
              <p class="wind-mode invisible">Height | <span
                  class="surface-wind text-button" id="isobaric-1000hPa">1000</span> – <span
                  class="surface-wind text-button" id="isobaric-850hPa">850</span> – <span
                  class="surface-wind text-button" id="isobaric-700hPa">700</span> – <span
                  class="surface-wind text-button" id="isobaric-500hPa">500</span> – <span
                  class="surface-wind text-button" id="isobaric-250hPa">250</span> – <span
                  class="surface-wind text-button" id="isobaric-70hPa">70</span> hPa
              </p>
              <p class="wind-mode invisible">Overlay | <span
                  class="text-button" id="overlay-ocean-off">None</span> – <span
                  class="text-button" id="overlay-wind" title="Wind">Wind</span> – <span
                  class="text-button" id="overlay-windtemp" title="Temperature">Temp</span>
              </p>
              <p>Projection | <span
                  class="proj text-button" id="atlantis" title="Atlantis">A</span> – <span
                  class="proj text-button" id="azimuthal_equidistant" title="Azimuthal Equidistant">AE</span> – <span
                  class="proj text-button" id="conic_equidistant" title="Conic Equidistant">CE</span> – <span
                  class="proj text-button" id="equirectangular" title="Equirectangular">E</span> – <span
                  class="proj text-button" id="orthographic" title="Orthographic">O</span> – <span
                  class="proj text-button" id="stereographic" title="Stereographic">S</span> – <span
                  class="proj text-button" id="waterman" title="Waterman Butterfly">WB</span> – <span
                  class="proj text-button" id="winkel3" title="Winkel Tripel">W3</span>
              </p>
          </div>
      </div>
      <script src="//cdnjs.cloudflare.com/ajax/libs/underscore.js/1.6.0/underscore-min.js" charset="utf-8"></script>
      <script src="//cdnjs.cloudflare.com/ajax/libs/backbone.js/1.1.0/backbone-min.js" charset="utf-8"></script>
      <script src="//cdnjs.cloudflare.com/ajax/libs/topojson/1.1.0/topojson.min.js" charset="utf-8"></script>
      <script src="//cdnjs.cloudflare.com/ajax/libs/d3/3.3.10/d3.min.js" charset="utf-8"></script>
  <!--
      <script src="/libs/underscore.js/1.6.0/underscore.js" charset="utf-8"></script>
      <script src="/libs/backbone.js/1.1.0/backbone.js" charset="utf-8"></script>
      <script src="/libs/topojson/1.1.0/topojson.js" charset="utf-8"></script>
      <script src="/libs/d3/3.3.10/d3.js" charset="utf-8"></script>
  -->
      <script src="/libs/d3.geo/0.0.0/d3.geo.projection.v0.min.js" charset="utf-8"></script>
      <script src="/libs/d3.geo/0.0.0/d3.geo.polyhedron.v0.min.js" charset="utf-8"></script>
      <script src="/libs/when/2.6.0/when.js" charset="utf-8"></script>
      <script src="/libs/earth/1.0.0/micro.js" charset="utf-8"></script>
      <script src="/libs/earth/1.0.0/globes.js" charset="utf-8"></script>
      <script src="/libs/earth/1.0.0/products.js" charset="utf-8"></script>
      <script src="/libs/earth/1.0.0/earth.js" charset="utf-8"></script>
      <!-- <script>
        var button = document.getElementById("ocean-mode-enable");
        function simulateButtonClick() {
            button.click();
        }
        window.onload = function() {
            simulateButtonClick();
        };
      </script> -->
  </body>
</html>
