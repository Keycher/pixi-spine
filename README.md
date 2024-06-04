# pixi-spine

Spine 3.7, 3.8, 4.0, 4.1 implementation for PixiJS V8. 

### Versions Compatibility

| PixiJS | pixi-spine |
|---|---|
| v8.x | v5.x |

### Bundles example PIXI v8

```js
import {Spine} from "pixi-spine";
import {Application, Assets, Text} from "pixi.js";

var app = new Application(1000, 800, {backgroundColor: 0x111111});

(async () => {
	await app.init();
	app.stage.interactive = true;
	document.body.appendChild(app.view);

	const spineGameLogo = await Assets.load('assets/Animation.json');

	const spine = new Spine(spineGameLogo.spineData);

	app.stage.addChild(spine);
	spine.position.set(app.renderer.width * 0.5, app.renderer.height * 0.5);
	spine.state.setAnimation(0, "AnimationName", true);

})();
```

If you have enough rights to publish this monorepo, you can publish by running `npm run lernaPublish`
This is so that it runs with the internal npm v8 since npm v9 doesn't play nice with Lerna.

If for some reason your publish failed, use `npm run lernaPublish:fromPackage` to try to force a publish without creating a new version
