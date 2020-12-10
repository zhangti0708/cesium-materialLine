# cesium-materialLine
基于cesium自定义材质线插件

----------------------------------------------------------------------------------------------------------------------------------------
### 基于cesium的自定义材质线插件
### cesium-materialLine

### 说明
##### /cesium-materialLine/src/doc

### 使用

#####  在项目中引入Cesium.js

#####  然后引入 cesium-materialLine.js 即可


<a href="http://zhangticcc.gitee.io/webgis/"><img alt="" height="100%" src="https://img-blog.csdnimg.cn/20201210131337623.gif" width="90%" ></a>&nbsp;

```
      // 自定义纹理材质
      let MaterialLineImage = [
        './src/line.png',
        './src/line2.png',
        './src/line3.png',
      ]

      // color
      let colors = [
        new Cesium.Color(77 / 255, 201 / 255, 255 / 255, 1),
        new Cesium.Color(255 / 255, 201 / 255, 38 / 255, 1),
        new Cesium.Color(221 / 255, 221 / 255, 221 / 255, 1)
      ];

      // 创建材质线
      let getCustomMaterialLine = (image, color) => {
        return new Cesium.CustomMaterialLine({
          image: image,
          color: color,
          duration: 2000
        })
      }
      // 添加实体线
      let startPoint = Cesium.Cartesian3.fromDegrees(104.081701757991, 30.627042558105988)
      let glowingLine = null
      for (let i = 0, len = 8; i < len; i++) {

        let endPoint = Cesium.Cartesian3.fromDegrees((Math.random() / 100) +
          104.081701757991, (Math.random() / 100) + 30.627042558105988);
        glowingLine = viewer.entities.add({
          polyline: {
            positions: [startPoint, endPoint],
            width: 5,
            material: getCustomMaterialLine(MaterialLineImage[i % 3], colors[i % 3]),
          }
        });
      }

```
