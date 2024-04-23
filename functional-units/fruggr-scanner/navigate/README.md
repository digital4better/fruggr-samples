# "navigate" functional unit with Fruggr scanner sample

## Requirements

Read the [main requirements](../#requirements).

## How to use?

- [Go on Fruggr SaaS](https://www.fruggr.io/app)
- Create a new Fruggr digital service of type "Functional Unit"
- Configure the functional unit script with the content [of this file](sample-funit-script.json)
- Copy the file `.env.sample` and name it `.env`
- Configure the `FRUGGR_API_KEY` in the `.env` file [with your one](https://wiki.fruggr.io/hc/fr/articles/9694438970653)
- Run `docker compose up`
- At the end of the analysis, [go on Fruggr SaaS](https://www.fruggr.io/app) and check the summary!
