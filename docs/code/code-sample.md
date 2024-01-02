# Sample Code

This page provides some sample code which may be used in your example component.

This code uses TypeScript, and the Markdown code fence to wrap the code.

```typescript
const serviceEntityPage = (
  <EntityLayout>
    <EntityLayout.Route path="/" title="Overview">
      <Grid container spacing={3} alignItems="stretch">
        <Grid item md={6}>
          <EntityAboutCard variant="gridItem" />
        </Grid>
      </Grid>
    </EntityLayout.Route>
    <EntityLayout.Route path="/docs" title="Docs">
      <EntityTechdocsContent />
    </EntityLayout.Route>
  </EntityLayout>
);
```

Here is an example of Python code:

```python
def getUsersInGroup(targetGroup, secure=False):

    if __debug__:
        print('targetGroup=[' + targetGroup + ']')
```

```python
from airflow.providers.google.cloud.operators.bigquery import BigQueryGetDatasetTablesOperator

get_dataset_tables = BigQueryGetDatasetTablesOperator(
     task_id='get_dataset_tables',
     dataset_id='my_airflow_002',
     # Use `bq_lob_default` string value.
     # This will point to a connection, created for your DAG in a runtime.
     gcp_conn_id='bq_lob_default',
     # Use `GLOBAL_IMPERSONATE_CHAIN` variable.
     # This global variable with the correct value will be provided during the DAG render.
     impersonation_chain=GLOBAL_IMPERSONATE_CHAIN,
)

start = DummyOperator(task_id='start')
end = DummyOperator(task_id='end')

start >> get_dataset_tables >> end
```

```python
launch_flex_template = DataflowStartFlexTemplateOperator(
  task_id='launch_flex_template',
  location='us-east1',
  body={
      'launchParameter': {
          'containerSpecGcsPath': '{{params.gcs_path + "/" + dag_run.conf.get("version") + "/dataflow.json" if \
                                  dag_run.conf.get("version") is not none else params.flex_template_gcs_path}}',
          'jobName': f'dataflow-{ENV}',
          'parameters': {
              'param': 'param value'
          },
          'environment': {
              'subnetwork': env_vars[ENV]['subnetwork'],
              'ipConfiguration': 'WORKER_IP_PRIVATE',
              'tempLocation': '{{params.gcs_path + "/" + dag_run.conf.get("version") + "/tmp" if \
                              dag_run.conf.get("version") is not none else params.tmp_location}}',
          }
      }
  },
  params={
      "gcs_path": gcs_path,
      "flex_template_gcs_path": flex_template_gcs_path,
      "staging_location": staging_location,
      "tmp_location": tmp_location
  }
  )
```

YAML example:

```yaml
parentKey:
  level1Key1: level1Value1
  level1Key2: level1Value2
  level1Key3:
    level2Key1: level2Value1
    level2_items:
      - item1Key1: item1Value1
        item1Key2: item1Value2
      - item2Key1: item2Value1
        item2Key2: item2Value2
  level1Key4: level1Value4
```

```yaml
airflow:
  enabled: true
  dag_folder: dags/
```

```yaml
airflow:
  enabled: true
  dag_folder: dags/
  env:
    sit:
      kpo:
        - name: foo
          image: gcr.io/qt-shared-services-3w/foo:v1.0.0-sit
        - name: bar
          image: gcr.io/qt-shared-services-3w/bar:v1.0.0-sit
        - name: foobar
          image: gcr.io/qt-shared-services-3w/foobar:v1.0.0-sit
```

## Table

| Key                     |  Required?   | Description                                                                                                                                                                                                                                                                                                                         |  Default Value  |
|-------------------------|:------------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------:|
| `enabled`               |  *optional*  | Must be set to `true` to enable Airflow                                                                                                                                                                                                                                                                                             |     `false`     |
| `dag_folder`            |  *required*  | Relative path from your root folder where the DAG files are located.                                                                                                                                                                                                                                                                |       `-`       |
| `env.{env}`             |  *optional*  | Dictionary of per `env` configuration. Allowed values are: `sit`, `uat` and `prod`.                                                                                                                                                                                                                                                 |      `{}`       |
| `env.{env}.kpo[]`       |  *optional*  | List of KPO configurations. Please check the [KPO section](#kubernetespodoperator) section for details.                                                                                                                                                                                                                             |      `[]`       |
| `env.{env}.kpo[].name`  |  *required*  | This will be the unique identifier of your KPO image pod template. The template generate by pipeline will be this name suffixed by `.yaml`. e.g. the example below will generate 3 pod templates by pipeline: `foo.yaml`, `bar.yaml` and `foobar.yaml`. Please check the [KPO section](#kubernetespodoperator) section for details. |       `-`       |
| `env.{env}.kpo[].image` |  *required*  | The docker image used by the KPO. Please check the [KPO section](#kubernetespodoperator) section for details.                                                                                                                                                                                                                       |       `-`       |


| Environment | Link                                                                                    |
|-------------|-----------------------------------------------------------------------------------------|
| SIT         | <https://app.nonprod.astronomer.q3.questech.io/w/cl1435gf300506miz37qpj1xp/d/airflow-sit> |
| SIT2        | **not supported** |
| UAT         | <https://app.nonprod.astronomer.q3.questech.io/w/cl1435gf300506miz37qpj1xp/d/airflow-uat> |
| LT        | **not supported** |
| PROD        | <https://app.prod.astronomer.q3.questech.io/w/cl3c5208o05626mcwraqpeaek/d/airflow-prod>   |


