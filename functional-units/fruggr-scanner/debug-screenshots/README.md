
# Run a functional unit with debug screenshots

## Use-case

This sample illustrates how generate debug screenshots while the scanner is running a functional unit analysis.

## Requirements

Read the [main requirements](../#requirements).

## How to use?

- [Go on Fruggr SaaS](https://www.fruggr.io/app)
- Create a new Fruggr digital service of type "Functional Unit"
- Configure the functional unit script with the content of [this sample file](sample-funit-script.json)
- Copy the file [`.env.sample`](.env.sample) and name it `.env`
- Configure the `FRUGGR_API_KEY` (check [requirements](#requirements)) in the `.env` file
- Run `docker compose up` in your command line
- At the end of the analysis, [go on Fruggr SaaS](https://www.fruggr.io/app) and check the summary of the analysis!

Screenshots are generated in the `work/screenshots` folder.

## Troubleshooting / FAQ

See ["Troubleshooting / FAQ"](../#troubleshooting--faq) section.

## Getting help

See ["Getting Help"](../#getting-help) section.
