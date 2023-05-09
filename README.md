<!DOCTYPE html>
<html>
<head>
	<title>Team Wither Battle</title>
	<style>
		body {
			background-color: #f2f2f2;
			font-family: Arial, sans-serif;
			font-size: 16px;
			margin: 0;
			padding: 0;
			text-align: center;
		}
		h1 {
			font-size: 36px;
			margin-top: 50px;
		}
		.team-container {
			display: flex;
			flex-wrap: wrap;
			justify-content: space-evenly;
			margin-top: 50px;
		}
		.team {
			border: 2px solid #000;
			border-radius: 5px;
			margin: 20px;
			padding: 20px;
			width: 400px;
		}
		.team.red {
			background-color: #ff4d4d;
		}
		.team.blue {
			background-color: #4d4dff;
		}
		.team.green {
			background-color: #4dff4d;
		}
		.team.yellow {
			background-color: #ffff4d;
		}
		.team h2 {
			color: #fff;
			font-size: 24px;
			margin: 0;
			padding: 10px;
			text-transform: uppercase;
		}
		.wither {
			cursor: pointer;
			display: inline-block;
			margin: 10px;
			position: relative;
			width: 150px;
		}
		.wither img {
			max-width: 100%;
		}
		.wither .health {
			background-color: #000;
			color: #fff;
			font-size: 14px;
			left: 0;
			padding: 5px;
			position: absolute;
			text-align: center;
			top: -20px;
			width: 100%;
		}
	</style>
</head>
<body>
	<h1>Team Wither Battle</h1>
	<div class="team-container">
		<div class="team red">
			<h2>Red Team</h2>
			<div class="withers">
				<div class="wither" data-health="1000">
					<img src="https://i.imgur.com/CW29Hgz.jpeg" alt="Red Wither">
					<div class="health">1000</div>
				</div>
			</div>
		</div>
		<div class="team blue">
			<h2>Blue Team</h2>
			<div class="withers">
				<div class="wither" data-health="1000">
					<img src="https://i.imgur.com/CW29Hgz.jpeg" alt="Blue Wither">
					<div class="health">1000</div>
				</div>
			</div>
		</div>
		<div class="team green">
			<h2>Green Team</h2>
			<div class="withers">
				<div class="wither" data-health="1000">
					<img src="https://i.imgur.com/CW29Hgz.jpeg" alt="Green Wither">
					<div class="health">1000</div>
				</div>
			</div>
		</div>
		<div class="team yellow">
			<h2>Yellow Team</h2>
			<div class="withers">
				<div class="wither"
data-health="1000">
<img src="https://i.imgur.com/CW29Hgz.jpeg" alt="Yellow Wither">
<div class="health">1000</div>
</div>
</div>
</div>
</div>
<script>
const withers = document.querySelectorAll('.wither');	withers.forEach(wither => {
		wither.addEventListener('click', () => {
			const health = wither.getAttribute('data-health');
			const damage = Math.floor(Math.random() * 9) + 3;
			const newHealth = health - damage;
			wither.setAttribute('data-health', newHealth);
			wither.querySelector('.health').textContent = newHealth;
			if (newHealth <= 0) {
				wither.parentElement.parentElement.innerHTML = "<h2>TEAM WITHER IS ELIMINATED! FINAL KILL!</h2>";
			}
		});
	});
</script>
</body>
</html>
