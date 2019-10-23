<script>

	import MyNav from "../components/MyNav.svelte";
	import Drawer, {AppContent, Content, Header, Title, Subtitle, Scrim} from '@smui/drawer';
	import Button, {Label} from '@smui/button';
	import List, {Item, Text, Graphic, Separator, Subheader} from '@smui/list';
	import H6 from '@smui/common/H6.svelte';

	export let segment;

	let active2 = 'Inbox';
	let myDrawer2;
	let myDrawer2Open = true;

	function setActive2(value) {
		active2 = value;
	}

	const appName = 'Pendataan Port Sampling'
</script>

<style>
	main {
		position: relative;
		margin: 0 auto;
		/*box-sizing: border-box;*/
	}

	@media screen and (max-width: 599px) {
		.drawer-container {
			margin-top: 56px;
			height: 100%;
			position: fixed;
			width: 100%;
			z-index: 0;
		}
	}

	@media screen and (min-width: 600px) {
		.drawer-container {
			margin-top: 64px;
			height: 100%;
			position: fixed;
			width: 100%;
			z-index: 0;
		}
	}


	.app-content {
		overflow-y: auto;
		overflow-x: hidden;
		padding: 16px;
		height: calc(100vh - 97px);
	}
</style>


<div>
	<MyNav {appName}/>

</div>

<div class="drawer-container">
	<!-- DRAWER -->
	<Drawer variant="dismissible" bind:this={myDrawer2} bind:open={myDrawer2Open}>
		<Header>
			<Title>Super Mail</Title>
			<Subtitle>It's the best fake mail app drawer.</Subtitle>
		</Header>
		<Content>
			<List>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Inbox')} activated={active2 === 'Inbox'}>
					<Graphic class="material-icons" aria-hidden="true">inbox</Graphic>
					<Text>Inbox</Text>
				</Item>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Star')} activated={active2 === 'Star'}>
					<Graphic class="material-icons" aria-hidden="true">star</Graphic>
					<Text>Star</Text>
				</Item>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Sent Mail')}
					activated={active2 === 'Sent Mail'}>
					<Graphic class="material-icons" aria-hidden="true">send</Graphic>
					<Text>Sent Mail</Text>
				</Item>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Drafts')}
					activated={active2 === 'Drafts'}>
					<Graphic class="material-icons" aria-hidden="true">drafts</Graphic>
					<Text>Drafts</Text>
				</Item>

				<Separator nav/>
				<Subheader component={H6}>Labels</Subheader>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Family')}
					activated={active2 === 'Family'}>
					<Graphic class="material-icons" aria-hidden="true">bookmark</Graphic>
					<Text>Family</Text>
				</Item>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Friends')}
					activated={active2 === 'Friends'}>
					<Graphic class="material-icons" aria-hidden="true">bookmark</Graphic>
					<Text>Friends</Text>
				</Item>
				<Item href="javascript:void(0)" on:click={()=> setActive2('Work')} activated={active2 === 'Work'}>
					<Graphic class="material-icons" aria-hidden="true">bookmark</Graphic>
					<Text>Work</Text>
				</Item>
			</List>
		</Content>
	</Drawer>

	<AppContent >
		<div class="app-content">
			<Button on:click={()=> myDrawer2Open = !myDrawer2Open}><Label>Toggle Drawer</Label></Button>
			<main>
				<slot></slot>
			</main>
		</div>
	</AppContent>
</div>

