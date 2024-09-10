
# Run a functional unit when the script is local

## Use-case

This sample illustrates how to run a functional unit with the Fruggr scanner when the script is local.

Scenario:
- The local functional script you want to test is located at `./work/script.json` on your computer
- Fruggr scanner reads and validates the script and analyze the digital service
- When the script has an error, you get it in the console of the command line

Please note: 
- The scanner ignore the script configured **on Fruggr platform** for the configured digital service

## Requirements

Read the [main requirements](../#requirements).

## How to use?

- [Go on Fruggr SaaS](https://www.fruggr.io/app)
- Create a new Fruggr digital service of type "Functional Unit"
- Copy the file [`.env.sample`](.env.sample) and name it `.env`
- Configure the `FRUGGR_API_KEY` (check [requirements](#requirements)) in the `.env` file
- Replace the content of `./work/script.json` by your own script
- Run `docker compose up` in your command line

### Successful execution

You should see such output when your script is ok:

```
$ docker compose up
...
Attaching to fruggr-scanner-1
fruggr-scanner-1  | 2024-07-03T10:06:41.814Z [scanner] Using fruggr version ...
fruggr-scanner-1  | 2024-07-03T10:06:41.814Z [browser] Queuing with {
fruggr-scanner-1  |   "device": "Desktop Chrome",
fruggr-scanner-1  |   "headless": true,
fruggr-scanner-1  |   "proxy": "off",
fruggr-scanner-1  |   "stealthMode": true
fruggr-scanner-1  | }
fruggr-scanner-1  | 2024-07-03T10:06:42.209Z [scanner] Using chromium version: 112.0.5615.29
fruggr-scanner-1  | 2024-07-03T10:06:42.209Z [scanner] Retrieving config from https://www.fruggr.io
fruggr-scanner-1  | 2024-07-03T10:06:43.154Z [scanner] Config retrieved for 'Local debug project'
fruggr-scanner-1  | 2024-07-03T10:06:43.155Z [scanner] A file has been provided to be a functional unit script: /home/myuser/dev/fgr/fruggr-samples/functional-units/fruggr-scanner/local-script-analyzing/work/script.json
fruggr-scanner-1  | 2024-07-03T10:06:43.155Z [Functional Unit Test] Validating functional unit script
...
fruggr-scanner-1  | 2024-07-03T10:07:10.789Z [scanner] Functional unit analysis done
fruggr-scanner-1  | 2024-07-03T10:07:10.789Z [Aggregation] Computing scores
fruggr-scanner-1  | 2024-07-03T10:07:10.791Z [Aggregation] Generating advices
fruggr-scanner-1  | 2024-07-03T10:07:10.794Z [scanner] Sending audit to https://www.fruggr.io
fruggr-scanner-1  | 2024-07-03T10:07:11.402Z [scanner] Audit sent
fruggr-scanner-1 exited with code 0
```

## Troubleshooting / FAQ

See ["Troubleshooting / FAQ"](../#troubleshooting--faq) section.

## Getting help

See ["Getting Help"](../#getting-help) section.
