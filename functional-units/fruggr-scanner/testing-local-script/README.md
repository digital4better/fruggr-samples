
# Test a functional unit when the script is local

## Use-case

This sample illustrates how develop and test a local functional unit script with the Fruggr scanner.

Scenario:
- The local functional script you want to test is located at `./work/script.json` on your computer
- Fruggr scanner is started in a special mode which allows it to read this local file
- Fruggr scanner reads and validates the script **without analyzing** the digital service
- When the script has an error, you get it in the console of your command line

## Requirements

Read the [main requirements](../#requirements).

Despite no analysis is done

## How to use?

- [Go on Fruggr SaaS](https://www.fruggr.io/app)
- Create a new Fruggr digital service of type "Functional Unit"
- Copy the file [`.env.sample`](.env.sample) and name it `.env`
- Configure the `FRUGGR_API_KEY` (check [requirements](#requirements)) in the `.env` file
- Run `docker compose up` in your command line

### Successful execution

You should see such output when your script is ok.

```
$ docker compose up
...
Attaching to fruggr-scanner-1
fruggr-scanner-1  | 2024-04-16T14:55:55.153Z [scanner] Using fruggr version ...
fruggr-scanner-1  | 2024-04-16T14:55:55.154Z [browser] Queuing with {
fruggr-scanner-1  |   "device": "Desktop Chrome",
fruggr-scanner-1  |   "headless": true,
fruggr-scanner-1  |   "proxy": "off",
fruggr-scanner-1  |   "stealthMode": true
fruggr-scanner-1  | }
fruggr-scanner-1  | 2024-04-16T14:55:55.566Z [scanner] Using chromium version: 112.0.5615.29
fruggr-scanner-1  | 2024-04-16T14:55:55.566Z [scanner] Retrieving config from https://www.fruggr.io
fruggr-scanner-1  | 2024-04-16T14:55:56.755Z [scanner] Config retrieved for 'Local debug project'
fruggr-scanner-1  | 2024-04-16T14:55:56.755Z [scanner] Debug mode enabled
fruggr-scanner-1  | 2024-04-16T14:55:56.755Z [scanner] Debug screenshots will be saved in /tmp/fruggr/screenshots
fruggr-scanner-1  | 2024-04-16T14:55:56.756Z [Functional Unit Test] Validating functional unit script
fruggr-scanner-1  | 2024-04-16T14:55:56.841Z [scanner] Functional unit local script test starting
fruggr-scanner-1  | 2024-04-16T14:55:56.841Z [Functional Unit Test] Setting up test for local script '/tmp/fruggr/script.json'
fruggr-scanner-1  | 2024-04-16T14:55:56.842Z [browser] Queuing with {
fruggr-scanner-1  |   "device": "Desktop Chrome",
fruggr-scanner-1  |   "headless": true,
fruggr-scanner-1  |   "proxy": "automatic",
fruggr-scanner-1  |   "stealthMode": true
fruggr-scanner-1  | }
fruggr-scanner-1  | 2024-04-16T14:55:56.971Z [Functional Unit Test] Executing actions of step "Go to digital4better.com website"
fruggr-scanner-1  | 2024-04-16T14:55:56.972Z [Functional Unit Test] Step: Go to digital4better.com website, executing action {
fruggr-scanner-1  |   "type": "navigate",
fruggr-scanner-1  |   "value": "https://digital4better.com/",
fruggr-scanner-1  |   "headers": false
fruggr-scanner-1  | }
fruggr-scanner-1  | 2024-04-16T14:55:58.581Z [scanner] Saving screenshot '1713884..._0_0_post.jpg'...
fruggr-scanner-1  | 2024-04-16T14:55:58.605Z [Functional Unit Test] Test done in 1.611 seconds for 1 steps
fruggr-scanner-1 exited with code 0
```

### Execution with failure

Failure example:

```
docker compose up
...
Attaching to fruggr-scanner-1
fruggr-scanner-1  | 2024-04-16T15:21:32.506Z [scanner] Using fruggr version ...
...
fruggr-scanner-1  | 2024-04-16T15:21:33.789Z [Functional Unit Test] Step: Go to digital4better.com website, executing action {
fruggr-scanner-1  |   "type": "navigate",
fruggr-scanner-1  |   "value": "https://digital4better.co/",
fruggr-scanner-1  |   "headers": false
fruggr-scanner-1  | }
fruggr-scanner-1  | 2024-04-16T15:21:33.901Z [Functional Unit] Step: Go to digital4better.com website, unable to navigate to 'https://digital4better.co/' {
fruggr-scanner-1  |   "stack": "page.goto: net::ERR_NAME_NOT_RESOLVED at https://digital4better.co/\n=========================== logs ===========================\nnavigating to \"https://digital4better.co/\", waiting until \"load\"\n============================================================\n    at /opt/fruggr/dist/index.js:3817:20\n    at /opt/fruggr/dist/index.js:3671:71\n    at __webpack_modules__.998.__awaiter (/opt/fruggr/dist/index.js:3667:12)\n    at navigateAction (/opt/fruggr/dist/index.js:3812:60)\n    at /opt/fruggr/dist/index.js:3867:46\n    at /opt/fruggr/dist/index.js:3671:71\n    at __webpack_modules__.998.__awaiter (/opt/fruggr/dist/index.js:3667:12)\n    at executeAction (/opt/fruggr/dist/index.js:3864:59)\n    at /opt/fruggr/dist/index.js:12708:55\n    at /opt/fruggr/dist/index.js:12643:71\n    at __webpack_modules__.3815.__awaiter (/opt/fruggr/dist/index.js:12639:12)\n    at runSteps (/opt/fruggr/dist/index.js:12680:79)\n    at headless (/opt/fruggr/dist/index.js:12726:84)\n    at /opt/fruggr/dist/index.js:7486:19\n    at fulfilled (/opt/fruggr/dist/index.js:7247:58)",
...
fruggr-scanner-1  | 2024-04-16T15:21:33.920Z [scanner] Exiting...
fruggr-scanner-1 exited with code 1
```

## Troubleshooting / FAQ

See ["Troubleshooting / FAQ"](../#troubleshooting-faq) section.

## Getting help

See ["Getting Help"](../#getting-help) section.
