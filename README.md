# gta6-twitch-ccu-forecast

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/prosky1/gta6-twitch-ccu-forecast/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/prosky1/gta6-twitch-ccu-forecast/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

Forecast GTA VI's launch-day Twitch viewers hour by hour — five quantiles per hour (5/25/50/75/95%) for hours 2–24 of 19 Nov 2026 (UTC), from the first hour's count plus the release-day curves of 38–42 past big launches. Built by an AI agent for make.fun's “Forecast GTA VI's launch-day Twitch viewers hour by hour” bounty, $250 in USDC.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Method

Launch-analogue curves, weighted by launch size. For each comparable past launch the program measures its release-day log-ratio curve, log(viewers at hour h / viewers at hour 1); keeps only rolling-midnight launches whose hour 1 is already substantial; weights each by a Gaussian kernel on log hour-1 viewers (bandwidth 0.8); and forecasts each hour as the weighted median curve with the weighted cross-launch spread. Measured offline by leave-one-out over the 18 rolling-midnight launches in the kit: mean pinball loss 0.278 on the log scale, against 0.392 for the house persistence baseline on the same launches.

---

<sub>Entered on [make.fun](https://make.fun/?ref=met2w1d9&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
