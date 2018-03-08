three.js
========

中文版
由滴滴前端联盟维护

[![Gitter][gitter-badge]][gitter-badge-url]
[![Latest NPM release][npm-badge]][npm-badge-url]
[![License][license-badge]][license-badge-url]
[![Dependencies][dependencies-badge]][dependencies-badge-url]
[![Dev Dependencies][devDependencies-badge]][devDependencies-badge-url]

#### JavaScript 3D 库 ####

该项目的目的是创建一个易用、轻量级的3D库。此代码库提供了 &lt;canvas&gt;, &lt;svg&gt;, CSS3D 和 WebGL 渲染器.

[实例](http://threejs.online/examples/) &mdash;
[文档](http://threejs.online/docs/) &mdash;
[Wiki](https://github.com/mrdoob/three.js/wiki) &mdash;
[迁移](https://github.com/mrdoob/three.js/wiki/Migration-Guide) &mdash;
[帮助](http://stackoverflow.com/questions/tagged/three.js)

### 用法 ###

首先下载 [压缩版代码库](http://threejs.online/build/three.min.js) 并将其包含到你的HTML中，或安装并导入它。 [模块](http://threejs.online/docs/#manual/introduction/Import-via-modules),
另外也可以看[如何自己构建库](https://github.com/mrdoob/three.js/wiki/Build-instructions).

```html
<script src="js/three.min.js"></script>
```


这段代码创建了一个场景、一个摄像头和一个几何立方体，并将立方体添加到场景中。然后，它会为场景和摄像头创建一个`WebGL`渲染器，并将viewport添加到document.body元素中。最后，它会在镜头内展示几何立方体的动画效果。

```javascript
var camera, scene, renderer;
var geometry, material, mesh;

init();
animate();

function init() {

	camera = new THREE.PerspectiveCamera( 70, window.innerWidth / window.innerHeight, 0.01, 10 );
	camera.position.z = 1;

	scene = new THREE.Scene();

	geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
	material = new THREE.MeshNormalMaterial();

	mesh = new THREE.Mesh( geometry, material );
	scene.add( mesh );

	renderer = new THREE.WebGLRenderer( { antialias: true } );
	renderer.setSize( window.innerWidth, window.innerHeight );
	document.body.appendChild( renderer.domElement );

}

function animate() {

	requestAnimationFrame( animate );

	mesh.rotation.x += 0.01;
	mesh.rotation.y += 0.02;

	renderer.render( scene, camera );

}
```

如果以上代码顺利运行，你应该在看看这里。 [这里](https://jsfiddle.net/f2Lommf5/).

### 更改日志 ###

[发布](https://github.com/mrdoob/three.js/releases)


[gitter-badge]: https://badges.gitter.im/mrdoob/three.js.svg
[gitter-badge-url]: https://gitter.im/mrdoob/three.js
[npm-badge]: https://img.shields.io/npm/v/three.svg
[npm-badge-url]: https://www.npmjs.com/package/three
[license-badge]: https://img.shields.io/npm/l/three.svg
[license-badge-url]: ./LICENSE
[dependencies-badge]: https://img.shields.io/david/mrdoob/three.js.svg
[dependencies-badge-url]: https://david-dm.org/mrdoob/three.js
[devDependencies-badge]: https://img.shields.io/david/dev/mrdoob/three.js.svg
[devDependencies-badge-url]: https://david-dm.org/mrdoob/three.js#info=devDependencies
