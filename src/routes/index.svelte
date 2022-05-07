<script lang="ts">
	import ArcRotateCamera from 'svelte-babylon/components/Cameras/ArcRotateCamera/index.svelte';
	import Canvas from 'svelte-babylon/components/Canvas/index.svelte';
	import DirectionalLight from 'svelte-babylon/components/Lights/DirectionalLight/index.svelte';
	import HemisphericLight from 'svelte-babylon/components/Lights/HemisphericLight/index.svelte';
	import Custom from 'svelte-babylon/components/Objects/Custom/index.svelte';
	import Scene from 'svelte-babylon/components/Scene/index.svelte';
	import { Vector3 } from '@babylonjs/core/Maths/math.vector';
</script>

<Canvas
	antialiasing={true}
	engineOptions={{
		preserveDrawingBuffer: true,
		stencil: true
	}}
>
	<Scene>
		<HemisphericLight intensity={0.5} />
		<DirectionalLight
			intensity={0.25}
			direction={new Vector3(-10, -20, -10)}
			position={new Vector3(2, 6, 2)}
		/>
		<ArcRotateCamera target={new Vector3(0, 0, 0)} radius={30} beta={1} />
		<Custom url="/example.glb" />
	</Scene>
</Canvas>
