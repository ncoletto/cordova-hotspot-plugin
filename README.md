# Cordova HotSpot Plugin


[![Build Status](https://travis-ci.org/hypery2k/cordova-hotspot-plugin.svg?branch=master)](https://travis-ci.org/hypery2k/cordova-hotspot-plugin) [![npm version](https://badge.fury.io/js/cordova-plugin-hotspot.svg)](http://badge.fury.io/js/cordova-plugin-hotspot) [![Dependency Status](https://david-dm.org/hypery2k/cordova-hotspot-plugin.svg)](https://david-dm.org/hypery2k/cordova-hotspot-plugin) [![devDependency Status](https://david-dm.org/hypery2k/cordova-hotspot-plugin/dev-status.svg)](https://david-dm.org/hypery2k/cordova-hotspot-plugin#info=devDependencies) 

> A Cordova plugin for managing HotSpot networks on Android with Cordova 3.4.0 / API Level 19
 
[![NPM](https://nodei.co/npm/cordova-plugin-hotspot.png)](https://nodei.co/npm/cordova-plugin-hotspot/)

Feel free to **donate**

<a href='http://www.pledgie.com/campaigns/25442'><img alt='Click here to lend your support to: Owncloud Apps and make a donation at www.pledgie.com !' src='http://www.pledgie.com/campaigns/23447.png?skin_name=chrome' border='0' /></a>
<a target="_blank" href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=AGPGLZYNV6Y5S">
<img alt="" border="0" src="https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donateCC_LG.gif"/>
</img></a>

## Installation

```bash
$ cordova plugin add cordova-plugin-hotspot
```
## Usage

### Check if Plugin is available

```javascript
cordova.plugins.hotspot.isAvailable(
    function (isAvailable) {
        // alert('Service is not available') unless isAvailable;
    }
);
```

### Check if device is connected to internet
   
```javascript
cordova.plugins.hotspot.isConnectedToInternet(
   function () {
       // is connected
   },function () {
       // is not connected
   }
);
```

### Get connection configuration
   
```javascript
cordova.plugins.hotspot.getConnectionInfo(
   function (result) {
       // SSID
       // BSSID
       // linkSpeed
       // IPAddress
   },function () {
       // error
   }
);
```

### Get network configuration
   
```javascript
cordova.plugins.hotspot.getNetConfig(
   function (result) {
       // deviceIPAddress
       // deviceMacAddress
       // gatewayIPAddress
       // gatewayMacAddress
   },function () {
       // error
   }
);
```

### Ping a host
      
```javascript
cordova.plugins.hotspot.pingHost(ip,
  function (result) {
      if(result){
        // host is up
      } else {
        // host is not responsing
      }
  },function (error) {
      //
      // error details, e.g
      /*
        requestTimeout:true,
        stats: {
          packetLoss: 10.0, // in %
          min: 51.371, // in ms
          max: 156.643, // in ms,
          avg: 95.370 // in ms,
          stddev: 33.016 // in ms
        }
      */
  }
);
```

### Get MAC address of host
      
```javascript
cordova.plugins.hotspot.getMacAddressOfHost(ip,
  function (result) {
      if(result){
        // MAC address of host
      } else {
        // host is not responsing
      }
  },function () {
      // error
  }
);
```

### Check DNS is alive
      
```javascript
cordova.plugins.hotspot.isDnsLive(ip,
  function (live) {
      if(live){
        // DNS is live
      } else {
        // DNS is not live
      }
  },function () {
      // error
  }
);
```

### Check port is alive
      
```javascript
cordova.plugins.hotspot.isPortLive(ip,
  function (live) {
      if(live){
        // DNS is live
      } else {
        // DNS is not live
      }
  },function () {
      // error
  }
);
```

### Check if device is rooted
      
```javascript
cordova.plugins.hotspot.isRooted(function (rooted) {
      if(rooted){
        // device is rooted
      } else {
        // device is not rooted
      }
  },function () {
      // error
  }
);
```


### Hotspot functionality

#### Create Hotspot

```javascript
cordova.plugins.hotspot.createHotspot(ssid, mode, password, 
    function () {
        // Hotspot is created
    },function () {
        // Error
    }
);
```

#### Start Hotspot
   
```javascript
cordova.plugins.hotspot.startHotspot(
   function () {
       // Hotspot is started
   },function () {
       // Error
   }
);
```

#### Configure Hotspot
   
```javascript
cordova.plugins.hotspot.configureHotspot(ssid, mode, password, 
   function () {
       // Hotspot is configured
   },function () {
       // Error
   }
);
```

#### Stop Hotspot

```javascript
cordova.plugins.hotspot.stopHotspot(
    function () {
        // Hotspot is disabled
    },function () {
        // Error
    }
);
```

#### Check if Hotspot is enabled

```javascript
cordova.plugins.hotspot.isHotspotEnabled(
    function () {
        // Hotspot is on
    },function () {
        // Hotspot is off
    }
);
```

#### Get all connected devices

```javascript
cordova.plugins.hotspot.getAllHotspotDevices(
    function (devices) {
        // array of JSON objects:
        // -> ip
        // -> mac
    },function (err) {
        // error
    }
);
```

### Wifi

### Check if Wifi is supported
   
```javascript
cordova.plugins.hotspot.isWifiSupported(
   function () {
       // wifi is on
   },function () {
       // wifi is off
   }
);
```

#### Check if Wifi is enabled
   
```javascript
cordova.plugins.hotspot.isWifiOn(
   function () {
       // wifi is on
   },function () {
       // wifi is off
   }
);
```

#### Toggle Wifi
   
```javascript
cordova.plugins.hotspot.toggleWifi(
   function (isActive) {
       // wifi is on
   },function (err) {
       // error
   }
);
```

#### Connect to Wifi
   
```javascript
cordova.plugins.hotspot.connectToHotspot(ssid, password, 
   function () {
       // connected
   },function () {
       // not connected
   }
);
```

### Check if device is connected to internet via Wifi
   
```javascript
cordova.plugins.hotspot.isConnectedToInternetViaWifi(
   function () {
       // is connected
   },function () {
       // is not connected
   }
);
```

### Check if Wifi Direct is supported

```javascript
cordova.plugins.hotspot.isWifiDirectSupported(
    function () {
        // wifi is on
    },function () {
        // wifi is off
    }
);
```

#### Add a network config
     
  ```javascript
  cordova.plugins.hotspot.addWifiNetwork(ssid, mode, password,
     function () {
         // wifi is added
     },function (err) {
         // error
     }
  );
```

#### Delete a network config
     
  ```javascript
  cordova.plugins.hotspot.removeWifiNetwork(ssid, 
     function () {
         // wifi is deleted
     },function (err) {
         // error
     }
  );
```

#### Start a periodically scan
     
  ```javascript
  cordova.plugins.hotspot.startPeriodicallyScan(interval, duration,
     function () {
         // success
     },function (err) {
         // error
     }
  );
```

#### Scan network
     
  ```javascript
  cordova.plugins.hotspot.scanWifi( 
     function (listOfNetworks) {
         // array of results
     },function (err) {
         // error
     }
  );
```

#### Scan network by level
     
  ```javascript
  cordova.plugins.hotspot.scanWifiByLevel(
     function (listOfNetworks) {
         // array of results
     },function (err) {
         // error
     }
  );
```

#### Stop a periodically scan
     
  ```javascript
  cordova.plugins.hotspot.stopPeriodicallyScan( 
     function () {
         // success
     },function (err) {
         // error
     }
  );
```

## Dev

### To run the integration tests before

```bash
export PLATFORM="android" 
./runIntegrationTests.sh
```
