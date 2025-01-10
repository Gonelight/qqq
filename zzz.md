# 1
<a href='https://postimages.org/' target='_blank'><img src='https://i.postimg.cc/3wNdDLSs/2025-01-09-17-03-13.jpg' border='0' alt='2025-01-09-17-03-13'/></a>

# 2
<img src="https://i.ibb.co/gJGM4Rc/Screenshot-2023-11-17-at-13-43-55.png">

# 3
<code>
{"message":"Got request","meta":{"params":{},"body":{"clientId":39933242,"message":"Не могу зарегистрироваться!","clientDeviceInfo":"Версия ОС: ios \nУстройство: iPhone XR \nВерсия приложения: 42.12.2","categoryId":"570","subcategoryId":"573","topic":"регистрация и разблокировка","action":"support","attachmentLinks":["https://s3.st.delitime.kz/support-dev/2023/07/07/79162317679/7040FF37-04BF-4761-9B01-B62B25470F78_1.jpg","https://s3.st.delitime.kz/support-dev/2023/07/07/79162317679/56B4B2E7-32EF-4300-9D5B-D3F6A5840287_2.jpg"],"isB2b":false,"rentId":90078729,"rentStage":"reserve"},"path":"/tickets","query":{}},"severity":"INFO","timestamp":1688726492740,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Check for existing ticket categoryId - 570 subCategoryId - 573 for client 39933242 before create new","severity":"INFO","timestamp":1688726492741,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Sending request to Eddy","meta":{"options":{"url":"https://testanytimekz.helpdeskeddy.com/api/v2/tickets/","method":"GET","headers":{"Authorization":"(masked)"},"params":{"page":1,"status_list":"open,25","search":"79167777777","exact_search":"1","order_by":"date_created{asc}"},"responseType":"json","maxContentLength":null,"maxBodyLength":null},"requestId":"f267e495-9c33-4553-bf2c-f9d2971c5b4d"},"severity":"INFO","timestamp":1688726493017,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Successful response from Eddy received","meta":{"body":{"data":[],"pagination":{"total":0,"per_page":30,"current_page":1,"total_pages":0}},"requestId":"f267e495-9c33-4553-bf2c-f9d2971c5b4d"},"severity":"INFO","timestamp":1688726493259,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Finished processing eddy tickets, handled count: 0","severity":"INFO","timestamp":1688726493261,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Building ticket request","severity":"INFO","timestamp":1688726493261,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Searching client by id 39933242","severity":"INFO","timestamp":1688726493261,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Sending request to eddy to create ticket","severity":"INFO","timestamp":1688726493268,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Could not create ticket","meta":{"error":"Request failed with status code 403"},"severity":"ERROR","timestamp":1688726493285,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
{"message":"Sending back success response","meta":{"code":500,"payload":{"message":"Request failed with status code 403"}},"severity":"INFO","timestamp":1688726493285,"session-fingerprint":"20b2f1a5-bb06-4f7a-bc74-e879e893bedc","transaction":"no transaction","service":"eddy","process-fingerprint":"9b5aaecc-2655-4e45-af13-80c8f5bb345d"}
</code>

# 4

```sql
CREATE TABLE public.cars (
	id int4 NOT NULL,
	plate_number varchar(10) NULL,
	point geometry(POINT, 4326) NULL,
	status varchar(12) NULL,
	fuel_percent numeric(5,2) NOT NULL DEFAULT 0,
	CONSTRAINT cars_pkey PRIMARY KEY (id),
	CONSTRAINT cars_plate_number_key UNIQUE (plate_number)
);

CREATE TABLE public.car_commands_log (
	uuid uuid NOT NULL DEFAULT uuid_generate_v4(),
	car_id int4 NOT NULL,
	action_code varchar(64) NOT NULL,
	is_success bool NOT NULL,
	created_at timestamptz NULL DEFAULT CURRENT_TIMESTAMP,
	CONSTRAINT car_commands_log_pkey PRIMARY KEY (uuid)
);

```
