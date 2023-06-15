## Task 1 Create a Cloud BigQuery dataset and table Using Cloud Shell

import datasets `taxiriders`
```
bq mk taxirides
```

create `table` in Bigquery
```
bq mk \
--time_partitioning_field timestamp \
--schema ride_id:string,point_idx:integer,latitude:float,longitude:float,\
timestamp:timestamp,meter_reading:float,meter_increment:float,ride_status:string,\
passenger_count:integer -t taxirides.realtime
```

create a storage bucket #❓ what is the bucket acually mean?
```
export BUCKET_NAME=qwiklabs-gcp-00-55a3ef2315e1
```

```
gsutil mb gs://$BUCKET_NAME/
```

![[Q117_perform-foundational-data-ml-and-ai-tasks-in-google-cloud/attachments/20230615213106.png]]
## Task 2 DataFlow Run the pipeline
![[attachments/Pasted image 20230615205202.png]]

after this run you will see your table `realtime` in BigQuery and you can send SQL to query data
![[attachments/Pasted image 20230615210253.png]]
