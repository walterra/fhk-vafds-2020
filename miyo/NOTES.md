# Development Notes

## Explore MIYO REST API

- MIYO REST API Docs https://docs.google.com/document/d/1K3MOLDid8f9C-blYbd6N0WpCls5QpK_Wm0yAmLYJbzY/export?format=pdf
- Push the button on your MIYO cube.
- `http://<miyo-ip>/api/link` will return an API key.
- Note that the API key includes curly braces, don't forget to add them for requests!
- `http://<miyo-ip>/api/logging/entries?apiKey={xxx}` - get logging data
- `cat logging_entries.json | jq -c .params.history[]` - transform downloaded raw request response to NDJSON
- `curl -X GET -G "http://<miyo-ip>/api/logging/entries" -d "apiKey={xxx}" | jq -c .params.history[] > logging_entries_nd.json`
- `curl -X GET -G "http://<miyo-ip>/api/logging/entries" -d "apiKey={xxx}" | | jq -c .params.history[] | jq -c '{(.stateTypeId): .value|tonumber, timestamp}' > logging_entries_transform_nd.json`

## Jupyter notebooks

- Tutorial: https://www.dataquest.io/blog/jupyter-notebook-tutorial/
- `brew install jupyter numpy `
- `pip3 install pandas matplotlib seaborn`
