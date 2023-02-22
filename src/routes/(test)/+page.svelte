<script lang="ts">
	import Foo from '$lib/Foo.svelte';
	import { popup, type PopupSettings } from '@skeletonlabs/skeleton';

	let exampleMenu: PopupSettings = {
		event: 'click',
		target: 'exampleMenu',
		placement: 'top'
		// state: (e: any) => console.log('tooltip', e)
	};
</script>

<div>
  <!-- Removing the <Foo> wrapper resolves the issue. -->
	<Foo>
		<button class="btn variant-filled" use:popup={exampleMenu}>
			<span>Menu</span>
			<span class="badge bg-white/10 dark:bg-black/10">Tap</span>
		</button></Foo
	>
	<div class="card variant-filled-secondary p-4 w-72 shadow-xl" data-popup="exampleMenu">
		<!-- NOTE: Keep this wrapper, .space-y will affect the arrow -->
		<div class="space-y-4">
			<p class="font-bold">This is a <strong>Menu</strong> example.</p>
			<p>
				Lorem ipsum dolor sit amet consectetur, adipisicing elit. Dicta amet nam hic aspernatur cum
				porro praesentium. Voluptates velit ex ad eius sit! Sit deserunt ex accusamus quod fugit
				enim in?
			</p>
			<button class="btn variant-filled">Close Me</button>
		</div>
		<!-- Arrow -->
		<div class="arrow variant-filled-secondary" />
	</div>
</div>
