<script lang="ts">
	import '../../css/about.css';
	import Icon from '@iconify/svelte';

	var isCardVisable = false;

	let isHovered = false;
	const toggleHover = () => (isHovered = !isHovered);

	function toggleCard() {
		isCardVisable = !isCardVisable;
		console.log(isCardVisable);
	}

	// function scrollIntoView() {
	// 	const el = document.querySelector('.footer');
	// 	if (!el) return;
	// 	el.scrollIntoView({
	// 		behavior: 'smooth'
	// 	});
	// }
</script>

<div class="container">
	<div class="content">
		Lorem ipsum dolor, sit amet consectetur adipisicing elit. Aliquid mollitia tenetur totam
		corporis eligendi at vero aperiam assumenda nemo ducimus molestiae tempore, facere autem
		accusantium, nobis magnam nostrum, laudantium vitae deserunt! Beatae, incidunt nam! Ducimus
		dolorum eveniet velit nemo sint neque vitae itaque aliquid delectus inventore quisquam suscipit
		iure, aliquam nobis, alias eligendi, officiis dolor. Ut ipsum facere beatae velit eligendi
		itaque doloribus voluptatem exercitationem, repellat quisquam minus nemo voluptatibus asperiores
		eos totam voluptatum. Placeat dignissimos deserunt exercitationem autem cumque nemo culpa animi!
		Perferendis amet delectus possimus inventore cumque, recusandae harum itaque necessitatibus
		officia accusamus unde magni praesentium architecto quasi.

		<div class="footer-area">
			<!-- svelte-ignore a11y-mouse-events-have-key-events -->
			<button
				class="footer-btn"
				on:click={toggleCard}
				on:mouseover={toggleHover}
				on:mouseout={toggleHover}
			>
				<Icon icon="iconamoon:arrow-up-2" class="btn-icon" />
			</button>
		</div>
	</div>
	<div class="footer {isCardVisable ? 'active' : ''}">
		<Icon icon="mdi:human" width="100" height="100" />
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo mollitia, optio eos, quae
			necessitatibus voluptatem voluptatum velit maiores natus inventore, quasi consequuntur.
			Quibusdam, porro eveniet atque odio eius reprehenderit amet quis, eaque deleniti distinctio
			inventore aperiam vero recusandae sunt sapiente ex cupiditate. Fugit harum maxime asperiores,
			ea distinctio ducimus voluptatem numquam, voluptate cumque totam in adipisci. Quia nostrum,
			tempora perferendis molestiae illum nisi aliquam fuga nihil. Atque incidunt nihil porro sint
			mollitia cum eligendi a, blanditiis recusandae cumque, debitis harum vitae ratione quis alias
			quisquam expedita ab. Velit dolorem commodi provident alias autem suscipit vel ab, possimus,
			non ratione perspiciatis?
		</p>
	</div>
</div>
