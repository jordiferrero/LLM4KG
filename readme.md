# LLM for Knowledge Graph creation from unstructured text data

## Install and launch neo4j

To launch Neo4j locally, first ensure you have docker installed. Then, you can launch the database with the following docker command:

```bash
docker run \
    -p 7474:7474 -p 7687:7687 \
    -v $PWD/data:/data -v $PWD/plugins:/plugins \
    --name neo4j-apoc \
    -e NEO4J_apoc_export_file_enabled=true \
    -e NEO4J_apoc_import_file_enabled=true \
    -e NEO4J_apoc_import_file_use__neo4j__config=true \
    -e NEO4JLABS_PLUGINS=\[\"apoc\"\] \
    neo4j:latest
```

From here, you can open the db at [http://localhost:7474/](http://localhost:7474/). On this page, you will be asked to sign in. Use the default username/password of `neo4j` and `neo4j`.

Once you login for the first time, you will be asked to change the password. I changed it to `12345678`.

After this, you are ready to create your first property graph!


## Install an env to run langchain

Install dependencies
```bash
pip install --upgrade  -r requirements.txt
```

Then run `main.py`.

## References

Project adapted from https://python.langchain.com/v0.1/docs/use_cases/graph/constructing/

Also inspired by https://colab.research.google.com/github/run-llama/llama_index/blob/main/docs/docs/examples/property_graph/property_graph_advanced.ipynb#scrollTo=EL6tYUI14S3D

For the docker-compose setup see https://medium.com/@bhunia.payel0301/containerize-fastapi-application-with-neo4j-using-docker-compose-file-969bb728d28b