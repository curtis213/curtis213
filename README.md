[1](https://mail.google.com/mail/u/0?ui=2&ik=3f7f450ff5&attid=0.1&permmsgid=msg-a:r2426658132411560911&th=18fc031629de12c1&view=att&disp=safe&realattid=f_lwqnp15l0)
<!doctype html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>Oscillator</title>

		<meta
			name="viewport"
			content="width=device-width, initial-scale=1, maximum-scale=1"
		/>
		<link
			rel="icon"
			type="image/png"
			sizes="174x174"
			href="./favicon.png"
		/>

		<script src="https://cdnjs.cloudflare.com/ajax/libs/webcomponentsjs/2.4.3/webcomponents-bundle.js"></script>
		<link
			href="https://fonts.googleapis.com/css?family=Material+Icons&display=block"
			rel="stylesheet"
		/>
		<script src="../build/Tone.js"></script>
		<script src="./js/tone-ui.js"></script>
		<script src="./js/components.js"></script>
		<style type="text/css">
			tone-play-toggle {
				margin-bottom: 10px;
			}
		</style>
	</head>
	<body>
		<tone-example label="Oscillator">
			<div slot="explanation">
				The oscillator has 4 basic types which can be altered by setting
				the number of partials and partials array.
				<br /><br />
				<a
					href="https://tonejs.github.io/docs/latest/classes/Oscillator"
					>Tone.Oscillator</a
				>
				docs.
			</div>

			<div id="content">
				<tone-momentary-button></tone-momentary-button>
			</div>
		</tone-example>

		<script type="text/javascript">
			const osc = new Tone.Oscillator({
				type: "square",
				frequency: 440,
				volume: -16,
			}).toDestination();

			ui({
				tone: osc,
				parent: document.querySelector("#content"),
			});

			// bind the interface
			document
				.querySelector("tone-momentary-button")
				.addEventListener("down", () => osc.start());
			document
				.querySelector("tone-momentary-button")
				.addEventListener("up", () => osc.stop());
		</script>
	</body>
</html>
