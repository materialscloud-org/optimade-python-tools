# Use cases

## Serving a single database

The [Materials Project](https://materialsproject.org) uses `optimade-python-tools` alongside their existing API and MongoDB database, providing [OPTIMADE-compliant access](https://optimade.materialsproject.org) to highly-curated density-functional theory calculations across all known inorganic materials.

`optimade-python-tools` handles filter parsing, database query generation and response validation by running the reference server implementation with minimal configuration.

## Serving multiple databases

[Materials Cloud](https://materialscloud.org) uses `optimade-python-tools` as a library to provide an OPTIMADE API entry to archived computational materials studies, created with the [AiiDA](https://aiida.net) Python framework and published through their archive.
In this case, each individual study and archive entry has its own database and separate API entry.
The Python classes within the `optimade` package have been extended to make use of AiiDA and its underlying [PostgreSQL](https://postgresql.org) storage engine.

Details of this implementation can be found on GitHub at [aiidateam/aiida-optimade](https://github.com/aiidateam/aiida-optimade).

## Extending an existing API

[NOMAD](https://nomad-lab.eu/) uses `optimade-python-tools` as a library to add OPTIMADE API endpoints to an existing web app.
Their implementation uses the Elasticsearch database backend to filter on millions of structures from aggregated first-principles calculations provided by their users and partners.
NOMAD also uses the package to implement a GUI search bar that accepts the OPTIMADE filter language.
NOMAD uses the release versions of the `optimade-python-tools` package, performing all customisation via configuration and sub-classing.
