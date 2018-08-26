# vue-html-slider

[![npm][npm]][npm-url] 
[![downloads][downloads]][downloads-url]
[![license][license]][license-url]

A simple, light and configurable vue silder component.

[npm]: https://img.shields.io/npm/v/vue-html-slider.svg
[npm-url]: https://www.npmjs.com/package/vue-html-slider
[downloads]: https://img.shields.io/npm/dm/vue-html-slider.svg
[downloads-url]: https://npmcharts.com/compare/vue-html-slider?minimal=true
[license]: https://img.shields.io/npm/l/vue-html-slider.svg
[license-url]:https://github.com/git-onepixel/vue-html-slider/blob/master/LICENSE

## Installation
use npm
``` bash
npm install vue-html-slider
```
use yarn
``` bash
yarn add vue-html-slider
```

## Get Started
Just one property is required to start the slider. As follows.
``` bash
# vue template
<template> 
    <vue-html-slider :images="images"></vue-html-slider>
</template>
<script>
    import Slider from 'vue-html-slider';
    export default {
        components: {
            # register slider as a html tag.
            vue-html-slider: Slider
        },
        data() {
            return {
                images: [
                    {
                        src: 'http://path/to/a.png'
                    },
                    {
                        src: 'http://path/to/b.png'
                    }
                ]
            }
        }
    }
</script>

```
With the above operation, you can display a beautiful slider.
 
<video width="414" height="300" autoplay loop src=""></video>
 
## Advanced
Slider defines many properties for customizing what you want. You can set a `options` property to slider as follow.
```
<vue-html-slider :options="options"></vue-html-slider>
````
The `options` contains many properties. All properties are listed below.

| Property | Type | default/params | Description | 
| ------ | ------ | ------ | ------ | 
| index | Number | 0 |  Default image position index. |
| autoplay | Boolean | false | Whether autoplay, not implement. |
| interval | Number | 1000 |  Autoplay interval mills, not implement. |
| loop | Boolean | false | Playing slider with loop, not implement. |
| clsName | String | - | Apply a css class on image element. | 
| gapWidth | Number | 0 | You can set a gap between each image.|
| useFade | Boolean | false | Apply fade animation to image when appears. |
| lazyload | Boolean | false | The image will be loaded only appears, if true. |
| loading | String | - | It will be shown before loaded. A html template or characters are supported.| 
| error | String | - | It will be shown after load error. A html template or characters are supported.|   
| hideIndicator | Boolen | false | Whether hide page number on bottom of image. As well, it can display 20 indicators at most.| 
| isDebug | Boolean | false | In Debug mode, slider will print some log infos by `console.log`. |
| disableBounce | Boolen | false | Whether disable bounce when reached slider boundary. |
| changed | Function | current image |  It fired when image position changed. |
| click | Function | current image | A click event fired on image element. |
| longTap | Function | current image |  Long tap event on image element. |
| longTapEnd | Function | current image | When long tap event finished. |

## Pull-left / Pull-right
You can move more when reached slider left or right bounday if you set `disableBounce` false. So, you can listen the event by setting a `pull-left` or `pull-right` property to slider. As follows.
```
<vue-html-slider :pull-left="pullLeft" :pull-right="pullRight">
</vue-html-slider>
````
The `pull-left` and `pull-right` have three properties respectively as follows.
| Property | Type | params | Description | 
| ------ | ------ | ------ | ------ | 
| tpl | String | - |  A html template will be shown when beyond slider boundary. Characters are also supported. |
| pull | Function | x | A pull event will be fired continuously before released. |
| release | Function | x | A release event will be fired when released. |
The `pull` or `release` parameter `x` refers to the distance that page leaves the boundary which is a absolute value.

## Dependence
This component is developed by vue2 with less, so it needs the following npm packages for running in your project successfully.
```
"devDependencies": {
    "css-loader": "^0.28.4",
    "file-loader": "^0.11.2",
    "less": "^2.7.2",
    "less-loader": "^4.0.4",
    "style-loader": "^0.18.2",
    "url-loader": "^0.5.9",
    "vue-html-loader": "^1.2.4",
    "vue-loader": "^13.0.0",
    "vue-template-compiler": "^2.3.4"
},
"dependencies": {
    "vue": "^2.3.4"
}
```
As well, in order to apply it in your project easily, a vue demo project for this component. See [slider-demo](https://github.com/git-onepixel/slider-demo) for help.

## License
This project is licensed under the MIT License.
See the [LICENSE.md](https://github.com/git-onepixel/vue-html-slider/blob/master/LICENSE) file for details.