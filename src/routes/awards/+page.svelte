<script>
	import { Awards } from '$lib/components'
	import { waitForAll } from '$lib/utils/helper';
	import LinearProgress from '@smui/linear-progress';

    export let data;
    const {awardsData, teamManagersData} = data;

const goToSection = (section) => {
        const top = section.getBoundingClientRect().top + window.pageYOffset;
        window.scrollTo({left: 0, top, behavior: 'smooth'});
    }
</script>

<style>
    .awards {
        display: block;
        margin: 30px auto;
		width: 95%;
		max-width: 1000px;
		position: relative;
		z-index: 1;
		overflow-y: hidden;
    }

	.loading {
		display: block;
		width: 85%;
		max-width: 500px;
		margin: 80px auto;
	}

	.nothingYet {
		display: block;
		width: 85%;
		max-width: 500px;
		margin: 80px auto;
		text-align: center;
	}

	.awards {
        position: relative;
        z-index: 1;
        width: 92%;
        max-width: 800px;
        margin: 8em auto 10em;
    }

    h1 {
        font-size: 2em;
        line-height: 1.2em;
        text-align: center;
        margin: 2em 0 1.5em;
    }

    h2 {
        font-size: 1.5em;
        line-height: 1.2em;
    }

    h3 {
        text-decoration: underline;
        font-size: 1.3em;
        line-height: 1.2em;
    }

    h4 {
        text-decoration: underline;
        margin-left: 2em;
        font-size: 1.2em;
        line-height: 1.2em;
    }

    h5 {
        margin-left: 6em;
        font-size: 0.8em;
        line-height: 1.1em;
    }

    .subBlock {
        margin-left: 2.4em;
    }

    .sectionHeading {
        margin: 4em 0 1.5em;
    }

    .subSectionHeading {
        margin: 1.5em 0 1.5em;
    }

    .underscore {
        text-decoration: underline;
    }

    .right {
        text-align: right;
    }

    .positionMaximums td {
        min-width: 3em;
    }

    .noUnderscore {
        text-decoration: none;
    }

    .clickable {
        cursor: pointer;
    }

    .clickable:hover {
        color: #00316b;
    }

    p {
        color: #777;
    }
</style>

<div class="awards">
	{#await waitForAll(awardsData, teamManagersData) }
		<div class="loading">
			<p>Retrieving awards data...</p>
			<LinearProgress indeterminate />
		</div>
	{:then [podiums, leagueTeamManagers] }
		{#each podiums as podium}
			<Awards {podium} {leagueTeamManagers} />
		{:else}
			<p class="nothingYet">No seasons have been completed yet, so no awards have been earned...</p>
		{/each}
	{:catch error}
		<!-- promise was rejected -->
		<p>Something went wrong: {error.message}</p>
	{/await}
</div>


<h3>2025</h3>
    <p>Season 2025:</p>

    <ol>
        <li>Champion: Kevin</li>
        <li>Runner-Up: Steven</li>
        <li>Spud: Mario</li>
    </ol>

<h3>2024</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Zach</li>
        <li>Runner-Up: ReRe</li>
        <li>Spud: Bgar</li>
    </ol>

<h3>2023</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Zach</li>
        <li>Runner-Up: ReRe</li>
        <li>Spud: Tim</li>
    </ol>

<h3>2022</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Steven/Tyler - Tie</li>
        <li>Runner-Up: Tie</li>
        <li>Spud: Zach</li>
    </ol>

<h3>2021</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Ryan</li>
        <li>Runner-Up: Bgar</li>
        <li>Spud: Mario</li>
    </ol>

<h3>2020</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Troy</li>
        <li>Runner-Up: Kevin</li>
        <li>Spud: Blake</li>
    </ol>

<h3>2019</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Justin</li>
        <li>Runner-Up: Troy</li>
        <li>Spud: Kevin</li>
    </ol>

<h3>2018</h3>
    <p>Season 2024:</p>

    <ol>
        <li>Champion: Kevin</li>
        <li>Runner-Up: Tyler</li>
        <li>Spud: Matt</li>
    </ol>
