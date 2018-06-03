# nuxt-detect-ua

<p align="center">
  <a href="https://camo.qiitausercontent.com/d50f55237fc27bec84cbd86060cb9be1391cee78/687474703a2f2f696d672e736869656c64732e696f2f62616467652f6c6963656e73652d4d49542d626c75652e7376673f7374796c653d666c6174" target="_blank" rel="nofollow noopener">
    <img src="https://camo.qiitausercontent.com/d50f55237fc27bec84cbd86060cb9be1391cee78/687474703a2f2f696d672e736869656c64732e696f2f62616467652f6c6963656e73652d4d49542d626c75652e7376673f7374796c653d666c6174" alt="MIT License" data-canonical-src="http://img.shields.io/badge/license-MIT-blue.svg?style=flat">
  </a>
</p>

[Nuxt.js](https://nuxtjs.org/) module for handling User-Agent.

Forked from [nuxt-user-agent](https://github.com/fukuiretu/nuxt-user-agent).

## Setup

```bath
yarn add nuxt-detect-ua
```


```nuxt.config.js
module.exports = {
  modules: [
    'nuxt-detect-ua',
  ]
}
```

## Usage

### Component

##### asyncData

```
asyncData(context) {
  const deviceType = context.$ua.deviceType()
  return { deviceType }
}
```

##### methods/created/mounted/etc

```
methods: {
  something() {
    const deviceType = this.$ua.deviceType()
    this.deviceType = deviceType
  }
}
```

##### Store actions

```
// In store
{
  actions: {
    getDeviceType ({ commit }) {
      const deviceType = this.$ua.deviceType()
      commit('SET_DEVICE_TYPE', deviceType)
    }
  }
}
```

##### template

```
<template>
  <section>
    <div v-if="$ua.isFromPc()">
      <span>PC</span>
    </div>
    <div v-if="$ua.isFromSmartphone()">
      <span>Smartphone</span>
    </div>
    <div v-if="$ua.isFromMobilephone()">
      <span>Mobilephone</span>
    </div>
    <div v-if="$ua.isFromTablet()">
      <span>Tablet</span>
    </div>
    <div v-if="$ua.isFromAppliance()">
      <span>Appliance</span>
    </div>
    <div v-if="$ua.isFromCrawler()">
      <span>Crawler</span>
    </div>
  </section>
</template>
```

## Methods

|       method        |  type   |    example    |
| :-----------------: | :-----: | :-----------: |
|     deviceType      | string  |      pc       |
|         os          | string  |    Mac OSX    |
|      osVersion      | string  |    10.12.6    |
|       browser       | string  |    Chrome     |
|   browserVersion    | string  | 65.0.3325.181 |
|    browserVendor    | string  |    Google     |
|    isFromIphone     | boolean |     true      |
|     isFromIpad      | boolean |     true      |
|     isFromIpod      | boolean |     true      |
|      isFromIos      | boolean |     true      |
|    isFromAndroid    | boolean |     true      |
| isFromAndroidTablet | boolean |     true      |
| isFromWindowsPhone  | boolean |     true      |
|      isFromPc       | boolean |     true      |
|  isFromSmartphone   | boolean |     true      |
|  isFromMobilephone  | boolean |     true      |
|   isFromAppliance   | boolean |     true      |
|    isFromCrawler    | boolean |     true      |
|    isFromTablet     | boolean |     true      |


## License
The npm is available as open source under the terms of the [MIT License.](https://opensource.org/licenses/MIT)
