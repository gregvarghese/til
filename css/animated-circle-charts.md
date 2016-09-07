http://codepen.io/stefanjudis/pen/jawGn

# HTML


```
<div class="ui">
  <div class="ui__sidebar left">
    <div class="ui__person">
      <div class="ui__person__name">Stefan</div>
    </div>
    <nav class="ui__nav">
      <ul>
        <li class="ui__nav__item"><input id="navItemOverview" type="radio" name="selectedNav" checked="checked"><label class="entypo-chart-bar" for="navItemOverview" data-label="Overview">Overview</label>
        <li class="ui__nav__item"><input id="navItemRadio" type="radio" name="selectedNav"><label class="entypo-folder" for="navItemRadio" data-label="Files">Files</label>
        <li class="ui__nav__item"><input id="navItemPhotos" type="radio" name="selectedNav"><label class="entypo-docs" for="navItemPhotos" data-label="Photos">Photos</label>
        <li class="ui__nav__item"><input id="navItemMusic" type="radio" name="selectedNav"><label class="entypo-sound" for="navItemMusic" data-label="Music">Music</label>
        <li class="ui__nav__item"><input id="navItemLinks" type="radio" name="selectedNav"><label class="entypo-globe" for="navItemLinks" data-label="Links">Links</label>
      </ul>
    </nav>
  </div>
  <div class="ui__main">
    <div class="ui__sidebar right">
      <input class="ui__search__input" type="search" placeholder="search">
      <h2 class="ui__friendsList__headline">Online</h2>
      <ul class="ui__friendsList">
        <li class="ui__person__small">
          <div class="ui__person__name small online">Ute Inge</div>
        <li class="ui__person__small">
          <div class="ui__person__name away">Ulla Schmidt</div>
        <li class="ui__person__small">
          <div class="ui__person__name notDisturb">Harry Winter</div>
      </ul>
      <h2 class="ui__friendsList__headline">Offline</h2>
      <ul class="ui__friendsList">
        <li class="ui__person__small">
          <div class="ui__person__name small offline">Bob Calsow</div>
        <li class="ui__person__small">
          <div class="ui__person__name offline">Chris Brase</div>
        <li class="ui__person__small">
          <div class="ui__person__name offline">Tom Madler</div>
        <li class="ui__person__small">
          <div class="ui__person__name offline">Reni Jadi</div>
        <li class="ui__person__small">
          <div class="ui__person__name offline">Radl Black</div>
      </ul>
    </div>
    <main class="ui__main__content">
      <h1 class="ui__main__headline">Overview</h1>
      <div class="ui__timeline" width=548 height=224>
        
      </div>
      <ul class="ui__downloadList">
        <li class="ui__downloadList__item red" data-value=810 data-type=music>
          <div class="ui__downloadList__graphic" width=154 height=160></div>
          <h2 class="ui__downloadList__headline">Music</h2>
          <h3 class="ui__downloadList__subHeadline">120 Files</h3>
        <li class="ui__downloadList__item purple" data-value=958 data-type=photos>
          <div class="ui__downloadList__graphic" width=154 height=160></div>
          <h2 class="ui__downloadList__headline">Photos</h2>
          <h3 class="ui__downloadList__subHeadline">65 Files</h3>
        <li class="ui__downloadList__item cyan" data-value=587 data-type=files>
          <div class="ui__downloadList__graphic" width=154 height=160></div>
          <h2 class="ui__downloadList__headline">Files</h2>
          <h3 class="ui__downloadList__subHeadline">98 Files</h3>
      </ul>
    </main>
  </div>
</div>
```


# CSS


```
@import "compass/css3";

@import url(http://weloveiconfonts.com/api/?family=entypo);

/* zocial */
[class*="entypo-"]:before {
  font-family: 'entypo', sans-serif;
}

/*
 * variables
 */

$c-body: #2c2c2d;
$c-sidebarBright: #4a5463;
$c-sidebarDark: #22262e;

$c-borderBright: #aaa;
$c-borderDark: #777;

$c-signalGreen: #33aa6b;
$c-signalBlue: #18a8f1;
$c-signalOrange: #ec6941;
$c-signalRed: #e60012;

$c-redBright: #ff5440;
$c-redDark: #f1301a;
$c-purpleBright: #a8aff1;
$c-purpleDark: #777ec3;
$c-cyanBright: #62d6eb;
$c-cyanDark: #00a8c9;

// font stuff
$font-color: #dbdcdf;
$font-size: 16px;
$font-family: Sans-Serif;

// z-index stuff
$z-navItemLabel: 3;
$z-navItemSignal: 2;
$z-navItemBackground: 1;

* {
  &, &:before, &:after {
    box-sizing: border-box;
    -moz-box-sizing: border-box;
  }
}

body {
  min-width: 960px;
  background-color: $c-body;
  color: $font-color;
  font-size: $font-size;
  font-family: $font-family;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.ui {
  position: absolute;
  
  width: 960px;
  height: 600px;
  
  top: 50%;
  left: 50%;
  
  overflow: hidden;
  
  margin: -300px 0 0 -480px;
  
  @include box-shadow( 0 2em 6em #000 );

  .redBackgroundStop1 { stop-color: adjust-lightness( $c-redBright, 7 ); }
  .redBackgroundStop2 { stop-color: $c-redBright; }  
  .purpleBackgroundStop1 { stop-color: adjust-lightness( $c-purpleBright, 7 ); }
  .purpleBackgroundStop2 { stop-color: $c-purpleBright; }
  .cyanBackgroundStop1 { stop-color: adjust-lightness( $c-cyanBright, 7 ); }
  .cyanBackgroundStop2 { stop-color: $c-cyanBright; }
  .redForegroundStop1 { stop-color: adjust-lightness( $c-redBright, 35 ); }
  .redForegroundStop2 { stop-color: adjust-lightness( $c-redBright, 23 ); }
  .purpleForegroundStop1 { stop-color: adjust-lightness( $c-purpleBright, 17 ); }
  .purpleForegroundStop2 { stop-color: adjust-lightness( $c-purpleBright, 8 ); }
  .cyanForegroundStop1 { stop-color: adjust-lightness( $c-cyanBright, 29 ); }
  .cyanForegroundStop2 { stop-color: adjust-lightness( $c-cyanBright, 15 ); }
}

.ui__downloadList {
  margin: 1em 0 0 -3.333%;
}

.ui__downloadList__graphic {
  margin: 0.5em;
  height: 10em;
}

.ui__downloadList__headline {
  position: absolute;
  
  bottom: 1.25em;
  
  width: 100%;
  
  margin: 0;
  padding: 0;
  
  font-weight: 100;
  text-align: center;
  
  font-size: 1.75em;
  
  @include text-shadow( 0.1em 0.1em 0.2em $c-sidebarDark );
}

.ui__downloadList__backgroundCircle {
  fill: #fff;
}

.ui__downloadList__foregroundCircle {
  fill: #fff;
  stroke-width: 1px;
}

.ui__downloadList__item {
  position: relative;
  
  width: 30%;
  height: 15em;

  float: left;
  margin-left: 3.333%;
  background-color: blue;
  
  @include box-shadow( 0 0.75em 2.5em #222 );
  
  &.red {
    @include background-image(
      linear-gradient(right bottom, $c-redDark, $c-redBright )
    );
    
    .ui__downloadList__backgroundCircle {
      fill: url(#gradientBackgroundRed);
    }
    .ui__downloadList__foregroundCircle {
      fill: url(#gradientForegroundRed);
    }
  }
  
  &.purple {
    @include background-image(
      linear-gradient(right bottom, $c-purpleDark, $c-purpleBright )
    );  
    
    .ui__downloadList__backgroundCircle {
      fill: url(#gradientBackgroundPurple);
    }
    .ui__downloadList__foregroundCircle {
      fill: url(#gradientForegroundPurple);
    }
  }
  
  &.cyan {
    @include background-image(
      linear-gradient(right bottom, $c-cyanDark, $c-cyanBright )
     );
    
    .ui__downloadList__backgroundCircle {
      fill: url(#gradientBackgroundCyan);
    }
    .ui__downloadList__foregroundCircle {
      fill: url(#gradientForegroundCyan);
    }
  }
}

.ui__downloadList__subHeadline {
  position: absolute;
  
  bottom: 1.5em;
  
  width: 100%;
  
  margin: 0;
  padding: 0;
  
  font-weight: 100;
  font-size: 0.75em;
  
  text-align: center;
  
  @include text-shadow( 0.125em 0.125em 0.2em $c-sidebarDark );
}

.ui__friendsList {
  padding: 0 1.5em 0 0.5em;
}

.ui__friendsList__headline {
  margin: 1.25em;
  font-size: 0.8em;
  font-weight: 200;
}

.ui__main {
  width: 85%;
  height: 100%;
  float: left;

  @include background-image(
    linear-gradient(right, adjust-lightness( $c-sidebarDark, -5 ), adjust-lightness( $c-sidebarBright, 15 ) )
  );
}

.ui__main__content {
  width: 75%;
  
  padding: 2em;
}

.ui__main__headline {
  margin: 0;
  padding: 0;
  font-weight: 100;
  font-size: 1.75em;
}

.ui__nav {

}

.ui__nav__item {
  position: relative;
  
  padding: 1.5em 0;
  border-bottom: 1px solid $c-borderDark;
  
  @include transition(
    background-color 0.2s ease-in,
    color 0.2s ease-in
   );
  
  &:hover {
    color: $c-signalBlue;
  }
  
  input {
    display: none;
    
    &:checked {
      + label {
        &:before {
          position: absolute;
          content: '';
        
          width: 0.25em;
          height: 100%;
        
          left: 0;
          top: 0;
          
          margin: 0;
        
          background-color: $c-signalBlue;
          
          z-index: $z-navItemSignal;
        }
        
        &:after {
          left: 0;
        }
      }
    }
  }
  
  label {
    display: block;
    
    height: 2em;
    line-height: 2em;
    
    margin: 0 0.5em;
    padding: 0 0 0 3em;
    
    cursor: pointer;
    
    z-index: $z-navItemLabel;
    
    &:before {
      position: absolute;
      
      top: 50%;
      left: 0.5em;
      font-size: 2em;
      
      margin: -0.5em 0 0 0;
    }
    
    &:after {
      content: attr(data-label);
      position: absolute;
      
      width: 100%;
      height: 100%;
      
      top: 0;
      left: -100%;
      
      color: $c-signalBlue;
      line-height: 5em;
      
      padding: 0 0 0 2em;
      
      background-color: $c-sidebarDark;
      
      // would liked to use transformations
      // but doesn't seem to be supported 
      // on pseudo elements
      @include transition( left 0.2s ease-in );
      
      z-index: $z-navItemBackground;
    }
  }
}

.ui__sidebar {
  height: 100%;

  &.left {
    width: 15%;
    
    border-right: 1px solid $c-borderBright;
    
    background-color: $c-sidebarBright;
    @include background-image(  linear-gradient(left bottom, $c-sidebarDark, $c-sidebarBright ) );
  }
  
  &.right {
    width: 25%;

    border-left: 1px solid adjust-lightness( $c-borderDark, -20 );
  }
}

.ui__search__input {
  width: calc(100% - 4em);
  line-height: 2em;
  margin: 2em;
  
  background-color: $c-sidebarBright;
  border: 0;
  
  border-radius: 1em;
  
  font-style: italic;
  
  outline: 0;
  
  &::-webkit-input-placeholder {
    position: relative;
    color: transparent;
  
    &:before, &:after {
      position: absolute;
      color: adjust-lightness( $c-sidebarBright, 30 );
    }
    
    &:before {
      content: 'search...';
      
      left: 2em;
      top: 0;
      
      width: 100%;
      height: 100%;
    }
    
    &:after {
      content: "\1f526";
      
      top: 0;
      left: 0.25em;
      
      width: 1.6em;
      height: 1.6em;
      line-height: 1.6em;
      
      font-size: 1.25em;
      
      font-family: 'entypo', sans-serif;
      font-style: normal;
    }
  }
  
  &::-webkit-search-cancel-button {
    margin: 0 1em 0 0;
  }
}

.ui__person {
  padding: 1.5em 0;
  border-bottom: 1px solid $c-borderDark;
}

.ui__person__small {
  padding: 0.5em 0;
}

.ui__person__name {
  position: relative;
  
  margin: 0 1em 0 0.5em;
  padding: 0 0 0 2.5em;

  height: 2em;  
  line-height: 2em;
  
  cursor: pointer;
  
  &:hover {
    &:after {
      width: 0.75em;
      height: 0.75em;
      
      margin: -0.375em -0.175em 0 0;
    }
  }
  
  &.away {
    &:after {
      border: 0.125em solid $c-signalOrange;
    }
  }
  
  &.notDisturb {
    &:after {
      border: 0.125em solid $c-signalRed;
    }
  }
  
  &.online {
    &:after {
      border: 0.125em solid $c-signalGreen;
    }
  }
  
  &.offline {
    &:after {
      border: 0.125em solid $c-sidebarBright;
    }
  }
  
  &:before, &:after {
    position: absolute;
    
    top: 50%;
    
    border-radius: 50%;
  }
  
  &:before {
    content: url('http://gravatar.com/avatar/22725c2d3eb331146549bf0d5d3c050c?s=30');

    height: 2em;
    width: 2em;
    
    left: 0;
    
    margin: -1em 0 0 0;
    
    border: 0.125em solid #fff;
    
    overflow: hidden;
  }
  
  &:after {
    content: '';
    
    height: 0.5em;
    width: 0.5em;
   
    top: 50%;
    right: 0;
    
    margin: -0.25em 0 0 0;
    
    border: 0.125em solid $c-signalGreen;
    
    z-index: 1;
    
    @include transition(
      width 0.2s ease-in,
      height 0.2s ease-in,
      margin 0.2s ease-in
    );
  }
}

.ui__timeline {
  height: 14em;
  margin: 1em 0 0 0;
 
  .domain {
    display: none;
  }
  
  .tick {
    fill: $font-color;
    font-size: 0.8em;
  }
}

.ui__timeline__area {
  stroke-width: 0.125em;
  
  &.red {
    fill: rgba( $c-redDark, 0.7 );
    stroke: $c-redBright;
  }
  &.purple {
    fill: rgba( $c-purpleDark, 0.7 );
    stroke: $c-purpleBright;
  }
  &.cyan {
    fill: rgba( $c-cyanDark, 0.7 );
    stroke: $c-cyanBright;
  }
}

/*
 * Helper classes
 */
.left {
  float: left;
}

.right {
  float: right;
}
```


# JS

;( function( d3 ) {
  var data = [
    {
      date  : 'September 15',
      value : 515,
      type  : 'Music'
    },
    {
      date  : 'September 16',
      value : 618,
      type  : 'Music'
    },
    {
      date  : 'September 17',
      value : 498,
      type  : 'Music'
    },
    {
      date  : 'September 18',
      value : 1243,
      type  : 'Music'
    },
    {
      date  : 'September 19',
      value : 1033,
      type  : 'Music'
    },
    {
      date  : 'September 15',
      value : 135,
      type  : 'Photos'
    },
    {
      date  : 'September 16',
      value : 218,
      type  : 'Photos'
    },
    {
      date  : 'September 17',
      value : 798,
      type  : 'Photos'
    },
    {
      date  : 'September 18',
      value : 643,
      type  : 'Photos'
    },
    {
      date  : 'September 19',
      value : 533,
      type  : 'Photos'
    },
    {
      date  : 'September 15',
      value : 846,
      type  : 'Files'
    },
    {
      date  : 'September 16',
      value : 218,
      type  : 'Files'
    },
    {
      date  : 'September 17',
      value : 428,
      type  : 'Files'
    },
    {
      date  : 'September 18',
      value : 843,
      type  : 'Files'
    },
    {
      date  : 'September 19',
      value : 333,
      type  : 'Files'
    }
  ];
  /**
   * Function to kick of all fancy download circles
   */
  function visualizeDownloadCircles ( selector ) {

    var d3items    = d3.selectAll( selector ),
        d3graphics = d3items.select( '.ui__downloadList__graphic' ),
        
        svgElements;

    // remove old svg for the case there was one
    d3graphics.select( 'svg' ).remove();

    d3items.each( function( svg, index ) { 
      var d3item = d3.select( this );
          
      index++;
      
      drawDownloadCircle( d3item, index );
    } );
  }
  
  /**
   * Function to draw one particular 
   * download circle
   */
  function drawDownloadCircle( d3item, index ) {
    var d3container = d3item.select( '.ui__downloadList__graphic' ),
        value       = d3item.attr( 'data-value' ),
        type        = d3item.attr( 'data-type' ),
        width       = d3container.attr( 'width' ),
        height      = d3container.attr( 'height' ),
        
        // circle stuff
        twoPi  = 2 * Math.PI,
        radius = Math.min( width, height ) / 2 - 5,
        arcBackground = d3.svg.arc()
                          .startAngle( 0 )
                          .endAngle( function( d ) { return d.value * twoPi; } )
                          .outerRadius( radius - 10 )
                          .innerRadius( radius - 35 ),
        arcForeground = d3.svg.arc()
                          .startAngle( 0 )
                          .endAngle( function( d ) { return d.value * twoPi; } )
                          .outerRadius( radius )
                          .innerRadius( radius - 27 ),
        
        // value stuff
        currentValue = 0,
        progress     = 0,
        
        // animation stuff,
        duration = 3000;
    
    // string to number
    value = +value;
        
    // append new svg
    var svg = d3container.append( 'svg' )
                          .attr( 'width', width )
                          .attr( 'height', height )
                          .append( 'g' )
                          .attr(
                            'transform',
                            'translate(' + width / 2 + ',' + height / 2 + ')'
                          );
    
    // filter stuff
    /* For the drop shadow filter... */
    var defs = svg.append( 'defs' );

    var filter = defs.append( 'filter' )
                      .attr( 'id', 'dropshadow' )

    filter.append( 'feGaussianBlur' )
          .attr( 'in', 'SourceAlpha' )
          .attr( 'stdDeviation', 2 )
          .attr( 'result', 'blur' );
    filter.append( 'feOffset' )
          .attr( 'in', 'blur' )
          .attr( 'dx', 2 )
          .attr( 'dy', 3 )
          .attr( 'result', 'offsetBlur' );

    var feMerge = filter.append( 'feMerge' );

    feMerge.append( 'feMergeNode' )
            .attr( 'in", "offsetBlur' )
    feMerge.append( 'feMergeNode' )
            .attr( 'in', 'SourceGraphic' );
    // end filter stuff
    
    // gradient stuff    
    var gradientBackgroundRed = defs.append( 'linearGradient' )
                                    .attr( 'id', 'gradientBackgroundRed' )
                                    .attr( 'x1', '0' )
                                    .attr( 'x2', '0' )
                                    .attr( 'y1', '0' )
                                    .attr( 'y2', '1' );
    gradientBackgroundRed.append( 'stop' )
                        .attr( 'class', 'redBackgroundStop1' )
                        .attr( 'offset', '0%' );
    
    gradientBackgroundRed.append( 'stop' )
                        .attr( 'class', 'redBackgroundStop2' )
                        .attr( 'offset', '100%' ); 

    var gradientBackgroundPurple = defs.append( 'linearGradient' )
                                      .attr( 'id', 'gradientBackgroundPurple' )
                                      .attr( 'x1', '0' )
                                      .attr( 'x2', '0' )
                                      .attr( 'y1', '0' )
                                      .attr( 'y2', '1' );
    
    gradientBackgroundPurple.append( 'stop' )
                            .attr( 'class', 'purpleBackgroundStop1' )
                            .attr( 'offset', '0%' );
    
    gradientBackgroundPurple.append( 'stop' )
                            .attr( 'class', 'purpleBackgroundStop2' )
                            .attr( 'offset', '100%' ); 

    var gradientBackgroundCyan = defs.append( 'linearGradient' )
                                    .attr( 'id', 'gradientBackgroundCyan' )
                                    .attr( 'x1', '0' )
                                    .attr( 'x2', '0' )
                                    .attr( 'y1', '0' )
                                    .attr( 'y2', '1' );
    
    gradientBackgroundCyan.append( 'stop' )
                          .attr( 'class', 'cyanBackgroundStop1' )
                          .attr( 'offset', '0%' );
    
    gradientBackgroundCyan.append( 'stop' )
                          .attr( 'class', 'cyanBackgroundStop2' )
                          .attr( 'offset', '100%' );     

    var gradientForegroundRed = defs.append( 'linearGradient' )
                                    .attr( 'id', 'gradientForegroundRed' )
                                    .attr( 'x1', '0' )
                                    .attr( 'x2', '0' )
                                    .attr( 'y1', '0' )
                                    .attr( 'y2', '1' );
    gradientForegroundRed.append( 'stop' )
                        .attr( 'class', 'redForegroundStop1' )
                        .attr( 'offset', '0%' );
    
    gradientForegroundRed.append( 'stop' )
                        .attr( 'class', 'redForegroundStop2' )
                        .attr( 'offset', '100%' ); 

    var gradientForegroundPurple = defs.append( 'linearGradient' )
                                        .attr( 'id', 'gradientForegroundPurple' )
                                        .attr( 'x1', '0' )
                                        .attr( 'x2', '0' )
                                        .attr( 'y1', '0' )
                                        .attr( 'y2', '1' );
    
    gradientForegroundPurple.append( 'stop' )
                .attr( 'class', 'purpleForegroundStop1' )
                .attr( 'offset', '0%' );
    
    gradientForegroundPurple.append( 'stop' )
                .attr( 'class', 'purpleForegroundStop2' )
                .attr( 'offset', '100%' ); 

    var gradientForegroundCyan = defs.append( 'linearGradient' )
                            .attr( 'id', 'gradientForegroundCyan' )
                            .attr( 'x1', '0' )
                            .attr( 'x2', '0' )
                            .attr( 'y1', '0' )
                            .attr( 'y2', '1' );
    
    gradientForegroundCyan.append( 'stop' )
                .attr( 'class', 'cyanForegroundStop1' )
                .attr( 'offset', '0%' );
    
    gradientForegroundCyan.append( 'stop' )
                .attr( 'class', 'cyanForegroundStop2' )
                .attr( 'offset', '100%' );     
    // end gradient stuff
    
    

    var meter = svg.append( 'g' )
                    .attr( 'class', 'progress-meter' );
    
    meter.append( 'title' )
          .text( 'Progress meter showing amount of space used for ' + type );
    
    meter.data(
            [
              { value : .0,  index : .5 }
            ]
          )
          .append( 'path' )
          .attr( 'class', 'ui__downloadList__backgroundCircle' )
          .attr( 'd', arcBackground )
          .attr( 'filter', 'url(#dropshadow)' )
          .transition()
          .duration( duration )
          .attrTween( 'd', tweenArcBackground( { value : 1 } ) );
    

    var foreground = meter.data(
                            [
                              { value : .0, index: .5 }
                            ]
                          )
                          .append( 'path' )
                          .attr( 'stroke', '#fff' )
                          .attr( 'class', 'ui__downloadList__foregroundCircle' )
                          .attr( 'd', arcForeground )
                          .attr( 'filter', 'url(#dropshadow)' )
                          .transition()
                          .attr( 'stroke', '#aaa' )
                          .delay( 1000 * index )   
                          .duration( duration )
                          .attrTween( 'd', tweenArcForeground({ value : value / 1000 } ) );
    
    
    meter.data( [ 0 ] )
          .append( 'text' )
          .text ( 0 )
          .attr( 'font-size', '25px' )
          .attr( 'x', 0 )
          .attr( 'y', 0 )
          .attr( 'fill', '#fff' )
          .attr( 'text-anchor', 'middle' )
          .attr( 'filter', 'url(#dropshadow)' )
          .transition()
          .delay( 1000 * index )
          .duration( duration )
          .tween( 'text', tweenText( value ) );
   
    meter.append( 'text' )
          .attr( 'fill', '#fff' )
          .attr( 'x', 0 )
          .attr( 'y', 20 ) 
          .attr( 'text-anchor', 'middle' )
          .attr( 'filter', 'url(#dropshadow)' )
          .text( 'mb' );

    
    // Helper functions!!!
    function tweenArcForeground( b ) {
      return function( a ) {
        var i = d3.interpolate( a, b );

        return function( t ) {
          return arcForeground( i ( t ) );
        };
      };
    }
    
    function tweenArcBackground( b ) {
      return function( a ) {
        var i = d3.interpolate( a, b );

        return function( t ) {
          return arcBackground( i ( t ) );
        };
      };
    }
    
    function tweenText( b ) {
      return function( a ) {
        var i = d3.interpolateRound( a, b );

        return function(t) {
          this.textContent = i(t);
        };
      }
    }
  }
  
  /**
   * Function to kick off drawing
   * the timeline graphic
   */
  function visualizeDownloadTimeline( selector, data ) {
    var d3container = d3.select( selector ),
        width       = d3container.attr( 'width' ),
        height      = d3container.attr( 'height' ),
        margin      = { top : 5, right : 0, bottom : 30, left : 0 },
        svg         = d3container.append( 'svg' )
                                  .attr( 'height', height )
                                  .attr( 'width', width ),
    
        x     = d3.scale.ordinal()
                        .rangeRoundBands( [ 0, width ] )
                        .domain(
                          data.map( function( d ) { return d.date; } )
                        ),
        xAxis = d3.svg.axis().scale( x ).orient( 'bottom' ),
        
        y     = d3.scale.linear()
                        .range( [ height - margin.bottom * 1.5, margin.top ] )
                        .domain(
                          [ 0, d3.max( data, function( d ) { return d.value; } ) ]
                        ),
        yAxis = d3.svg.axis().scale( y ).orient( 'left' ),
        
        xAxisGroup,
        yAxisGroup,
        
        // animation stuff,
        duration = 3000;
    
    xAxisGroup = svg.append( 'g' )
                    .attr( 'class', 'x axis' )
                    .attr( 'transform', 'translate( 0,' + ( height - margin.bottom ) + ')' )
                    .transition()
                    .call( xAxis );
    
    // filter stuff
    /* For the drop shadow filter... */
    var defs = svg.append( 'defs' );

    var filter = defs.append( 'filter' )
                      .attr( 'id', 'dropshadowArea' )

    filter.append( 'feGaussianBlur' )
          .attr( 'in', 'SourceAlpha' )
          .attr( 'stdDeviation', 3 )
          .attr( 'result', 'blur' );
    filter.append( 'feOffset' )
          .attr( 'in', 'blur' )
          .attr( 'dx', 2 )
          .attr( 'dy', 2 )
          .attr( 'result', 'offsetBlur' );

    var feMerge = filter.append( 'feMerge' );

    feMerge.append( 'feMergeNode' )
            .attr( 'in", "offsetBlur' )
    feMerge.append( 'feMergeNode' )
            .attr( 'in', 'SourceGraphic' );
    // end filter stuff
    
    drawArea(
      svg,
      data.filter(
        function( datum ) { return datum.type === 'Music'; }
      ),
      'red',
      1
    );
    
    drawArea(
      svg,
      data.filter(
        function( datum ) { return datum.type === 'Photos'; }
      ),
      'purple',
      2
    );
    
    drawArea(
      svg,
      data.filter(
        function( datum ) { return datum.type === 'Files'; }
      ),
      'cyan',
      3
    );
    
    function drawArea( svg, data, className, index ) {
      var area = d3.svg.area()
                        .x( function( d ) { return x( d.date ) + x.rangeBand() / 2 ; } )
                        .y0( height - margin.bottom * 1.5 )
                        .y1( function( d ) { return y( d.value ); } )
                        .interpolate( 'cardinal' ),
          startData = [];
      
      // if you know a better way please tell me. ;)
      // js deep "copy"
      data.forEach( function( datum ) {
        startData.push( { date : datum.date, value : 0 } );
      } );
      
      svg.append( 'path' )
          .datum( startData )
          .attr( 'class', 'ui__timeline__area ' + className )
          .attr( 'd', area )
          .attr( 'filter', 'url(#dropshadowArea)' )
          .transition()
          .delay( 1000 * index )   
          .duration( duration )
          .attrTween( 'd', tweenArea( data ) );
      
      
      // Helper functions!!!
      function tweenArea( b ) {
        return function( a ) {
          var i = d3.interpolateArray( a, b );          
          a.forEach( function( datum, index ) {
            a[ index ] = b[ index ]
          } );

          return function( t ) {
            return area( i ( t ) );
          };
        };
      }
    }
  }
  
  function ಠ_ಠ() {
    visualizeDownloadCircles( '.ui__downloadList__item' );
    visualizeDownloadTimeline( '.ui__timeline', data );
  }
  
  // yeah, let's kick things off!!!
  ಠ_ಠ();
} )( d3 );