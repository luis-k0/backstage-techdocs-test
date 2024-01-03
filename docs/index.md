## Table

### 4 lines

| Key                                                     | Required?  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       | Default Value |
|:--------------------------------------------------------|:----------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------:|
| `pubsubs_to_subscribe[]`                                | *optional* | List of topic names that a subscription will be created, and the application will be granted with permissions to subscribe. This list can be a list of strings with the topic names, or a list of objects for advanced configuration.                                                                                                                                                                                                             |     `[]`      |
| `pubsubs_to_subscribe[].name`                           | *required* | The topic name for which the subscription will be created.                                                                                                                                                                                                                                                                                                                                                                                        |       -       |
| `pubsubs_to_subscribe[].enableMessageOrdering`          | *optional* | Whether the subscription will be configured with [Message Ordering](#message-ordering). Can be `true` or `false`.                                                                                                                                                                                                                                                                                                                                 |    `false`    |
| `pubsubs_to_subscribe[].ackDeadlineSeconds`             | *optional* | This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the message. To override this value for a given message, call subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify is 10 seconds. The maximum custom deadline you can specify is 600 seconds.                                                                    |     `10`      |

### Original Key Left

| Key                                                     | Required?  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       | Default Value |
|:--------------------------------------------------------|:----------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------:|
| `pubsubs_to_subscribe[]`                                | *optional* | List of topic names that a subscription will be created, and the application will be granted with permissions to subscribe. This list can be a list of strings with the topic names, or a list of objects for advanced configuration.                                                                                                                                                                                                             |     `[]`      |
| `pubsubs_to_subscribe[].name`                           | *required* | The topic name for which the subscription will be created.                                                                                                                                                                                                                                                                                                                                                                                        |       -       |
| `pubsubs_to_subscribe[].enableMessageOrdering`          | *optional* | Whether the subscription will be configured with [Message Ordering](#message-ordering). Can be `true` or `false`.                                                                                                                                                                                                                                                                                                                                 |    `false`    |
| `pubsubs_to_subscribe[].ackDeadlineSeconds`             | *optional* | This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the message. To override this value for a given message, call subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify is 10 seconds. The maximum custom deadline you can specify is 600 seconds.                                                                    |     `10`      |
| `pubsubs_to_subscribe[].messageRetentionDuration`       | *optional* | How long to retain unacknowledged messages in the subscription's backlog, from the moment a message is published. Cannot be more than 7 days ('"604800s"') or less than 10 minutes ('"600s"')                                                                                                                                                                                                                                                     |   `604800s`   |
| `pubsubs_to_subscribe[].retainAckedMessages`            | *optional* | Indicates whether to retain acknowledged messages. If 'true', then messages are not expunged from the subscription's backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.                                                                                                                                                                                                                          |    `false`    |
| `pubsubs_to_subscribe[].expirationPolicyTtl`            | *optional* | A policy that specifies the conditions for this subscription's expiration. A subscription is considered active as long as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the subscription.  The minimum allowed value for expirationPolicy.ttl is 1 day.                                                                                                                           |     `31`      |
| `pubsubs_to_subscribe[].subscriptionSuffix`             | *optional* | The suffix for a subscription. Mandatory when having multiple subscriptions to a same topic. See [Multiple Subscriptions To Same Topic](#multiple-subscriptions-to-same-topic)                                                                                                                                                                                                                                                                    |      ``       |
| `pubsubs_to_subscribe[].filter`                         | *optional* | Configures the [Message Filtering](#message-filtering) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                 |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy`                    | *optional* | A policy that specifies how Pub/Sub retries message delivery for this subscription. If not set, the default retry policy is applied. This generally implies that messages will be retried as soon as possible for healthy subscribers. RetryPolicy will be triggered on NACKs or acknowledgement deadline exceeded events for a given message.                                                                                                    |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy.maximumBackoff`     | *optional* | The maximum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |    `600s`     |
| `pubsubs_to_subscribe[].retryPolicy.minimumBackoff`     | *optional* | The minimum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |     `10s`     |
| `pubsubs_to_subscribe[].deadLetter`                     | *optional* | Configures a [Dead Letter Queue](#dead-letter-queue) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                   |    `null`     |
| `pubsubs_to_subscribe[].deadLetter.enabled`             | *optional* | Enable the [Dead Letter Queue](#dead-letter-queue).                                                                                                                                                                                                                                                                                                                                                                                               |    `false`    |
| `pubsubs_to_subscribe[].deadLetter.maxDeliveryAttempts` | *optional* | The maximum number of delivery attempts for any message. The value must be between 5 and 100. The number of delivery attempts is defined as 1 + (the sum of number of NACKs and number of times the acknowledgement deadline has been exceeded for the message). A NACK is any call to ModifyAckDeadline with a 0 deadline. Note that client libraries may automatically extend ack_deadlines. This field will be honored on a best effort basis. |      `5`      |

### Original Key Center

| Key                                                     | Required?  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       | Default Value |
|:-------------------------------------------------------:|:----------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------:|
| `pubsubs_to_subscribe[]`                                | *optional* | List of topic names that a subscription will be created, and the application will be granted with permissions to subscribe. This list can be a list of strings with the topic names, or a list of objects for advanced configuration.                                                                                                                                                                                                             |     `[]`      |
| `pubsubs_to_subscribe[].name`                           | *required* | The topic name for which the subscription will be created.                                                                                                                                                                                                                                                                                                                                                                                        |       -       |
| `pubsubs_to_subscribe[].enableMessageOrdering`          | *optional* | Whether the subscription will be configured with [Message Ordering](#message-ordering). Can be `true` or `false`.                                                                                                                                                                                                                                                                                                                                 |    `false`    |
| `pubsubs_to_subscribe[].ackDeadlineSeconds`             | *optional* | This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the message. To override this value for a given message, call subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify is 10 seconds. The maximum custom deadline you can specify is 600 seconds.                                                                    |     `10`      |
| `pubsubs_to_subscribe[].messageRetentionDuration`       | *optional* | How long to retain unacknowledged messages in the subscription's backlog, from the moment a message is published. Cannot be more than 7 days ('"604800s"') or less than 10 minutes ('"600s"')                                                                                                                                                                                                                                                     |   `604800s`   |
| `pubsubs_to_subscribe[].retainAckedMessages`            | *optional* | Indicates whether to retain acknowledged messages. If 'true', then messages are not expunged from the subscription's backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.                                                                                                                                                                                                                          |    `false`    |
| `pubsubs_to_subscribe[].expirationPolicyTtl`            | *optional* | A policy that specifies the conditions for this subscription's expiration. A subscription is considered active as long as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the subscription.  The minimum allowed value for expirationPolicy.ttl is 1 day.                                                                                                                           |     `31`      |
| `pubsubs_to_subscribe[].subscriptionSuffix`             | *optional* | The suffix for a subscription. Mandatory when having multiple subscriptions to a same topic. See [Multiple Subscriptions To Same Topic](#multiple-subscriptions-to-same-topic)                                                                                                                                                                                                                                                                    |      ``       |
| `pubsubs_to_subscribe[].filter`                         | *optional* | Configures the [Message Filtering](#message-filtering) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                 |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy`                    | *optional* | A policy that specifies how Pub/Sub retries message delivery for this subscription. If not set, the default retry policy is applied. This generally implies that messages will be retried as soon as possible for healthy subscribers. RetryPolicy will be triggered on NACKs or acknowledgement deadline exceeded events for a given message.                                                                                                    |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy.maximumBackoff`     | *optional* | The maximum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |    `600s`     |
| `pubsubs_to_subscribe[].retryPolicy.minimumBackoff`     | *optional* | The minimum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |     `10s`     |
| `pubsubs_to_subscribe[].deadLetter`                     | *optional* | Configures a [Dead Letter Queue](#dead-letter-queue) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                   |    `null`     |
| `pubsubs_to_subscribe[].deadLetter.enabled`             | *optional* | Enable the [Dead Letter Queue](#dead-letter-queue).                                                                                                                                                                                                                                                                                                                                                                                               |    `false`    |
| `pubsubs_to_subscribe[].deadLetter.maxDeliveryAttempts` | *optional* | The maximum number of delivery attempts for any message. The value must be between 5 and 100. The number of delivery attempts is defined as 1 + (the sum of number of NACKs and number of times the acknowledgement deadline has been exceeded for the message). A NACK is any call to ModifyAckDeadline with a 0 deadline. Note that client libraries may automatically extend ack_deadlines. This field will be honored on a best effort basis. |      `5`      |

### Original Key Right

| Key                                                     | Required?  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       | Default Value |
|--------------------------------------------------------:|:----------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------:|
| `pubsubs_to_subscribe[]`                                | *optional* | List of topic names that a subscription will be created, and the application will be granted with permissions to subscribe. This list can be a list of strings with the topic names, or a list of objects for advanced configuration.                                                                                                                                                                                                             |     `[]`      |
| `pubsubs_to_subscribe[].name`                           | *required* | The topic name for which the subscription will be created.                                                                                                                                                                                                                                                                                                                                                                                        |       -       |
| `pubsubs_to_subscribe[].enableMessageOrdering`          | *optional* | Whether the subscription will be configured with [Message Ordering](#message-ordering). Can be `true` or `false`.                                                                                                                                                                                                                                                                                                                                 |    `false`    |
| `pubsubs_to_subscribe[].ackDeadlineSeconds`             | *optional* | This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the message. To override this value for a given message, call subscriptions.modifyAckDeadline with the corresponding ackId if using pull. The minimum custom deadline you can specify is 10 seconds. The maximum custom deadline you can specify is 600 seconds.                                                                    |     `10`      |
| `pubsubs_to_subscribe[].messageRetentionDuration`       | *optional* | How long to retain unacknowledged messages in the subscription's backlog, from the moment a message is published. Cannot be more than 7 days ('"604800s"') or less than 10 minutes ('"600s"')                                                                                                                                                                                                                                                     |   `604800s`   |
| `pubsubs_to_subscribe[].retainAckedMessages`            | *optional* | Indicates whether to retain acknowledged messages. If 'true', then messages are not expunged from the subscription's backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.                                                                                                                                                                                                                          |    `false`    |
| `pubsubs_to_subscribe[].expirationPolicyTtl`            | *optional* | A policy that specifies the conditions for this subscription's expiration. A subscription is considered active as long as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the subscription.  The minimum allowed value for expirationPolicy.ttl is 1 day.                                                                                                                           |     `31`      |
| `pubsubs_to_subscribe[].subscriptionSuffix`             | *optional* | The suffix for a subscription. Mandatory when having multiple subscriptions to a same topic. See [Multiple Subscriptions To Same Topic](#multiple-subscriptions-to-same-topic)                                                                                                                                                                                                                                                                    |      ``       |
| `pubsubs_to_subscribe[].filter`                         | *optional* | Configures the [Message Filtering](#message-filtering) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                 |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy`                    | *optional* | A policy that specifies how Pub/Sub retries message delivery for this subscription. If not set, the default retry policy is applied. This generally implies that messages will be retried as soon as possible for healthy subscribers. RetryPolicy will be triggered on NACKs or acknowledgement deadline exceeded events for a given message.                                                                                                    |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy.maximumBackoff`     | *optional* | The maximum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |    `600s`     |
| `pubsubs_to_subscribe[].retryPolicy.minimumBackoff`     | *optional* | The minimum delay between consecutive deliveries of a given message. Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |     `10s`     |
| `pubsubs_to_subscribe[].deadLetter`                     | *optional* | Configures a [Dead Letter Queue](#dead-letter-queue) for the subscription. Disabled by default.                                                                                                                                                                                                                                                                                                                                                   |    `null`     |
| `pubsubs_to_subscribe[].deadLetter.enabled`             | *optional* | Enable the [Dead Letter Queue](#dead-letter-queue).                                                                                                                                                                                                                                                                                                                                                                                               |    `false`    |
| `pubsubs_to_subscribe[].deadLetter.maxDeliveryAttempts` | *optional* | The maximum number of delivery attempts for any message. The value must be between 5 and 100. The number of delivery attempts is defined as 1 + (the sum of number of NACKs and number of times the acknowledgement deadline has been exceeded for the message). A NACK is any call to ModifyAckDeadline with a 0 deadline. Note that client libraries may automatically extend ack_deadlines. This field will be honored on a best effort basis. |      `5`      |

### With Div style

| <div style="width:450px">Key</div>                                                     | Required?  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                       | Default Value |
|:--------------------------------------------------------|:----------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------:|
| `pubsubs_to_subscribe[]`                                | *optional* | List of topic names that a subscription will be created, and the application will be granted with permissions to subscribe.<br>This list can be a list of strings with the topic names, or a list of objects for advanced configuration.                                                                                                                                                                                                             |     `[]`      |
| `pubsubs_to_subscribe[].name`                           | *required* | The topic name for which the subscription will be created.                                                                                                                                                                                                                                                                                                                                                                                        |       -       |
| `pubsubs_to_subscribe[].enableMessageOrdering`          | *optional* | Whether the subscription will be configured with [Message Ordering](#message-ordering). Can be `true` or `false`.                                                                                                                                                                                                                                                                                                                                 |    `false`    |
| `pubsubs_to_subscribe[].ackDeadlineSeconds`             | *optional* | This value is the maximum time after a subscriber receives a message before the subscriber should acknowledge the message.<br>To override this value for a given message, call subscriptions.modifyAckDeadline with the corresponding ackId if using pull.<br>The minimum custom deadline you can specify is 10 seconds.<br>The maximum custom deadline you can specify is 600 seconds.                                                                    |     `10`      |
| `pubsubs_to_subscribe[].messageRetentionDuration`       | *optional* | How long to retain unacknowledged messages in the subscription's backlog, from the moment a message is published.<br>Cannot be more than 7 days ('"604800s"') or less than 10 minutes ('"600s"')                                                                                                                                                                                                                                                     |   `604800s`   |
| `pubsubs_to_subscribe[].retainAckedMessages`            | *optional* | Indicates whether to retain acknowledged messages.<br>If 'true', then messages are not expunged from the subscription's backlog, even if they are acknowledged, until they fall out of the messageRetentionDuration window.                                                                                                                                                                                                                          |    `false`    |
| `pubsubs_to_subscribe[].expirationPolicyTtl`            | *optional* | A policy that specifies the conditions for this subscription's expiration.<br>A subscription is considered active as long as any connected subscriber is successfully consuming messages from the subscription or is issuing operations on the subscription.<br>The minimum allowed value for expirationPolicy.ttl is 1 day.                                                                                                                           |     `31`      |
| `pubsubs_to_subscribe[].subscriptionSuffix`             | *optional* | The suffix for a subscription.<br>Mandatory when having multiple subscriptions to a same topic.<br>See [Multiple Subscriptions To Same Topic](#multiple-subscriptions-to-same-topic)                                                                                                                                                                                                                                                                    |      ``       |
| `pubsubs_to_subscribe[].filter`                         | *optional* | Configures the [Message Filtering](#message-filtering) for the subscription.<br>Disabled by default.                                                                                                                                                                                                                                                                                                                                                 |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy`                    | *optional* | A policy that specifies how Pub/Sub retries message delivery for this subscription.<br>If not set, the default retry policy is applied.<br>This generally implies that messages will be retried as soon as possible for healthy subscribers.<br>RetryPolicy will be triggered on NACKs or acknowledgement deadline exceeded events for a given message.                                                                                                    |    `null`     |
| `pubsubs_to_subscribe[].retryPolicy.maximumBackoff`     | *optional* | The maximum delay between consecutive deliveries of a given message.<br>Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |    `600s`     |
| `pubsubs_to_subscribe[].retryPolicy.minimumBackoff`     | *optional* | The minimum delay between consecutive deliveries of a given message.<br>Value should be between 0 and 600 seconds.                                                                                                                                                                                                                                                                                                                                   |     `10s`     |
| `pubsubs_to_subscribe[].deadLetter`                     | *optional* | Configures a [Dead Letter Queue](#dead-letter-queue) for the subscription.<br>Disabled by default.                                                                                                                                                                                                                                                                                                                                                   |    `null`     |
| `pubsubs_to_subscribe[].deadLetter.enabled`             | *optional* | Enable the [Dead Letter Queue](#dead-letter-queue).                                                                                                                                                                                                                                                                                                                                                                                               |    `false`    |
| `pubsubs_to_subscribe[].deadLetter.maxDeliveryAttempts` | *optional* | The maximum number of delivery attempts for any message.<br>The value must be between 5 and 100.<br>The number of delivery attempts is defined as 1 + (the sum of number of NACKs and number of times the acknowledgement deadline has been exceeded for the message).<br>A NACK is any call to ModifyAckDeadline with a 0 deadline.<br>Note that client libraries may automatically extend ack_deadlines.<br>This field will be honored on a best effort basis. |      `5`      |

### Originals for tests

| Key                     |  Required?   | Description                                                                                                                                                                                                                                                                                                                         |  Default Value  |
|-------------------------|:------------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:---------------:|
| `enabled`               |  *optional*  | Must be set to `true` to enable Airflow                                                                                                                                                                                                                                                                                             |     `false`     |
| `dag_folder`            |  *required*  | Relative path from your root folder where the DAG files are located.                                                                                                                                                                                                                                                                |       `-`       |
| `env.{env}`             |  *optional*  | Dictionary of per `env` configuration.<br>Allowed values are: `sit`, `uat` and `prod`.                                                                                                                                                                                                                                                 |      `{}`       |
| `env.{env}.kpo[]`       |  *optional*  | List of KPO configurations.<br>Please check the [KPO section](#kubernetespodoperator) section for details.                                                                                                                                                                                                                             |      `[]`       |
| `env.{env}.kpo[].name`  |  *required*  | This will be the unique identifier of your KPO image pod template.<br>The template generate by pipeline will be this name suffixed by<br>`.yaml`. e.g. the example below will generate 3 pod templates by pipeline:<br>`foo.yaml`, `bar.yaml` and `foobar.yaml`.<br>Please check the [KPO section](#kubernetespodoperator) section for details. |       `-`       |
| `env.{env}.kpo[].image` |  *required*  | The docker image used by the KPO.<br>Please check the [KPO section](#kubernetespodoperator) section for details.                                                                                                                                                                                                                       |       `-`       |


| Environment | Link                                                                                    |
|-------------|-----------------------------------------------------------------------------------------|
| SIT         | <https://app.nonprod.astronomer.q3.questech.io/w/cl1435gf300506miz37qpj1xp/d/airflow-sit> |
| SIT2        | **not supported** |
| UAT         | <https://app.nonprod.astronomer.q3.questech.io/w/cl1435gf300506miz37qpj1xp/d/airflow-uat> |
| LT        | **not supported** |
| PROD        | <https://app.prod.astronomer.q3.questech.io/w/cl3c5208o05626mcwraqpeaek/d/airflow-prod>   |

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

```cs
namespace HelloWorld;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
    }
}
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
