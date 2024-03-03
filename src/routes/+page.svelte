<script lang="ts">
    let yesno = 0;
    function toggleYes () {
        yesno = 1;
    }
    function toggleNo () {
        yesno = 2;
    }
</script>

<svelte:head>
	<title>my portfolio</title>
</svelte:head>

<body>
    <div class="welcome-title">
        Movie night as soon as you are available?
    </div>
    <img class="shy" src="https://cdn3.emoji.gg/emojis/3271-shy-face.png" alt="shy">
    <br><br>

    <button on:click={toggleYes}>
        Yes 🥰
    </button>

    <button on:click={toggleNo}>
        No 😡
    </button>

    <div class="ifr">
        {#if yesno==2}
    <iframe width="1280" height="739" src="https://www.youtube.com/embed/VaVYmPDKmww" title="Banana Cat Crying 10 Hours" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    {:else if yesno==1}
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/KN3IemyqJJw" title="Happy Happy Happy Cat 10 Hours" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    {/if}
    </div>

    
</body>

<style lang="scss">
    .ifr {
        position: relative;
        overflow: hidden;
        width: 100%;
        padding-top: 56.25%; /* 16:9 Aspect Ratio (divide 9 by 16 = 0.5625) */
    }

    /* Then style the iframe to fit in the container div with full height and width */
    iframe {
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        width: 100%;
        height: 100%;
    }
    .shy {
        max-width: 25%;
    }
    body {
        text-align: center;
        font-family: Noto Serif;
        color: #efefef;
    }
    :global(body) {
		background-color: #30323a;
	}
	.welcome-title {
		font-size: 3rem;

		text-align: center;
		margin-bottom: 2rem;
		color: var(--primary-text);
	}
	.textShadow {
		text-shadow: 2px 2px 12px rgb(36 36 36);
	}
	.sections-wrapper {
		padding: 4rem 0;
		font-family: "Noto Serif", serif;
		background-color: var(--primary);
		color: var(--primary-text);
	}
	.presentation {
		display: flex;
		flex: 1;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background-color: rgba(var(--RGB-primary), 0.9);
		backdrop-filter: blur(5px);
		z-index: 2;
	}
	:global(body) {
		scroll-behavior: smooth;
	}
	.docs-visit {
		color: var(--accent);
		display: flex;
		&:hover {
			text-decoration: underline;
		}
	}

	.links-row-wrapper {
		background-color: var(--secondary);
		color: var(--secondary-text);
		display: flex;
		justify-content: center;
	}
	.links-row {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		@media screen and (max-width: 650px) {
			display: flex;
			flex-wrap: wrap;
		}
	}
	.main {
		display: flex;
		flex-direction: column;
		/* 
		background-size: 400% 400%;
		animation: gradient 15s ease infinite;
		background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
		*/
		min-height: 100vh;
		border-radius: 0.6rem;
		.content {
			display: flex;
			flex: 1;
			border-radius: 0.4rem;
			overflow: hidden;
			position: relative;
			border-radius: 0.45rem;
		}
	}
	.preview-image {
		display: flex;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		position: absolute;
		background-image: url('/images/ASM-editor.webp');
		background-repeat: no-repeat;
		background-position: center;
		background-size: cover;
	}

	@media screen and (max-width: 650px) {
		.main {
			.content {
				width: 100%;
			}
		}
		.welcome-title {
			font-size: 2.5rem;
		}
	}

	@keyframes gradient {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
</style>