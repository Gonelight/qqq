# 1
<a href='https://postimages.org/' target='_blank'><img src='https://i.postimg.cc/3wNdDLSs/2025-01-09-17-03-13.jpg' border='0' alt='2025-01-09-17-03-13'/></a>

# 2 mobile
|  |  |
| ----------- | ----------- |
| <img src="https://i.ibb.co/Cv2fCwF/screenshot-2024-05-07-06-24-46-0000.jpg"> | <img src="https://i.ibb.co/HhGqVWK/screenshot-2024-05-07-06-25-52-0000.jpg"> |

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
	
# 5
	
```sql
CREATE TABLE public.metrics (
	id serial,
	user_id int4,
	status varchar(16),
	payment_density float8,
	penalty_density float8,
	ride_minutes float8,
	rents_count int4,	
	mileage jsonb NULL
	CONSTRAINT metrics_pkey PRIMARY KEY (id)
);
```
| Показатель    | Описание        | Ограничения |
| :------------ |:---------------:| -----:|
| status        | Статус пользователя | строка - active или blocked |
| payment_density      | Плотность оплаты счетов        | 0 - 1 |
| penalty_density | Плотность оплаты штрафов        |   0 - 1 |
| rents_count | Количество аренд        |  |
| ride_minutes | Количество минут в аренде        | |

# 6
	
```python
{
    "tariffs": {
        "items": [
            {
                "action": "selectTariff",
                "tariffId": "2554949",
                "confirmationData": {
                    "tariffType": "Minute"
                },
                "title": "Минуты — 17<superscript>64</superscript> ₽/мин",
                "subtitle": "поездка от 79 ₽ · от 8,66 ₽/мин в ожидании"
            },
            {
                "action": "selectTariffFix",
                "tariffId": "2554950",
                "confirmationData": {
                    "tariffType": "Fix"
                },
                "title": "Фикс",
                "subtitle": "указать адрес и узнать цену"
            },
            {
                "action": "selectTariffConstructor",
                "tariffId": "hours",
                "confirmationData": {
                    "tariffType": "Offer"
                },
                "title": "Часы",
                "additionalTitle": "от 526<superscript>04</superscript> ₽",
                "subtitle": "от 1 до 12 часов"
            },
            {
                "action": "selectTariffConstructor",
                "tariffId": "days",
                "confirmationData": {
                    "tariffType": "Offer"
                },
                "title": "Дни",
                "additionalTitle": "от 3647<superscript>26</superscript> ₽",
                "subtitle": "от 1 дня до месяца"
            }
        ]
    }
}



list1 = [
    {
        'id': 1,
        'name': 'Беспалова Агафья Никифоровна',
        'email': 'safonovgostomisl@example.net'
    },
    {
        'id': 2,
        'name': 'Соловьев Александр Васильевич',
        'email': 'nbeljaev@example.org'
    },
    {
        'id': 3,
        'name': 'Максимильян Викторович Бобылев',
        'email': 'shubinaevpraksija@example.com'
    },
    {
        'id': 4,
        'name': 'Нонна Архиповна Карпова',
        'email': 'kuzma_10@example.net'
    }
]

list2 = [
    {
        'id': 2,
        'name': 'Соловьев Александр Васильевич',
        'email': 'nbeljaev@example.org'
    },
    {
        'id': 1,
        'name': 'Беспалова Агафья Никифоровна',
        'email': 'safonovgostomisl@example.net'
    },
    {
        'id': 4,
        'name': 'Нонна Архиповна Карпова',
        'email': 'kuzma_10@example.net'
    },
    {
        'id': 3,
        'name': 'Максимильян Викторович Бобылев',
        'email': 'shubinaevpraksija@example.com'
    },
]

```

# 7

```js
const router = require('express').Router();
const Sequelize = require('sequelize')
const models = require('../models');
const notAllowed = {
  status: 'error',
  message: 'Method Not Allowed',
};

router.get('/users/validate/:login', async (req, res, next) => {
  if (req.access_role !== 'guido') {
    res.status(405).json(notAllowed);
    return true;
  }
  try {
    const { login } = req.params;
    const clients = models.clients;
    let result = {};

    if ( login.toString().length === 11 ) {
      let client = await clients.findOne({
        where: {
          login
        }
      });
      if (client && client.status === 2) {
        result = {status: 'success', message: 'Client is active and valid', client}
      } else {
        result = {status: 'error', message: 'Client is not valid', client}
      }
    } else {
      result = {status: 'error', message: 'Wrong client login'}
    }

    res.json(result);
  } catch (error) {
    next(error);
  }
});

module.exports = router;
```

# 8

```python
from datetime import datetime
from random import randint

from dateutil import parser
from flask import request
from pony.orm import db_session

from mocks.model import RentIncidents
from .incident_types import incident_types
from .utils import to_pm_format


@db_session
def incidents():
    started_after = parser.parse(request.args['startedAfter'])
    args = {}
    if client_id := request.args.get('customerIdentifier'):
        args['client_id'] = client_id
    if rent_id := request.args.get('rentIdentifier'):
        args['rent_id'] = rent_id

    query = RentIncidents.select(**args).filter(
        lambda i: i.created_at > started_after
    )

    limit = int(request.args['limit'])
    offset = int(request.args.get('offset', 0))
    items = [{
        'id': x.id,
        'type': {
            'identifier': x.identifier,
            'name': incident_types[x.identifier],
            'createdAt': '2022-11-11T08:27:34.430133Z',
            'updatedAt': '2022-11-11T08:27:34.430133Z'
        },
        'imei': '863921035420895',
        'customerIdentifier': str(x.client_id),
        'vehicleIdentifier': str(randint(99, 1000)),
        'rentIdentifier': str(x.rent_id),
        'info': {},
        'externalInfo': {},
        'status': 'Active',
        'startedAt': to_pm_format(x.created_at),
        'finishedAt': None,
        'createdAt': to_pm_format(x.created_at),
        'updatedAt': to_pm_format(x.updated_at),
        'startPoint': {
            'latitude': 59.93197,
            'longitude': 30.318832
        },
        'finishPoint': None,
    } for x in query][offset:limit + offset]
    return {
        'items': items,
        'total': len(items),
        'lastSyncAt': to_pm_format(datetime.now())
    }


```

# 9

```python
from dataclasses import dataclass
from typing import Optional


@dataclass
class User:
    first_name: str
    last_name: str
    age: int
    email: Optional[str] = None

    @staticmethod
    def to_camel_case(snake_str):
        first, *others = snake_str.split('_')
        return ''.join([first.lower(), *map(str.title, others)])

    def __str__(self):
        result = {}
        for attr in self.__dict__:
            key = self.to_camel_case(attr)
            value = getattr(self, attr)
            if value is not None:
                result[key] = value
        return str(result)


user = User('Владимир', 'Владимиров', 70)

print(user)
```

# 10

```
FROM git.delimobil.ru:5005/deploy/ci/node:11

RUN apt-get update && \
    apt-get install -y curl git
WORKDIR /usr/src/api/
COPY . /usr/src/api/
ENV TZ=Europe/Moscow
RUN npm i --unsafe-perm --verbose
CMD ["node", "app.js"]

```

# 11
```yaml
version: '3.7'

services:

  cars-service:
    container_name: cars.service
    build:
      context: .
      dockerfile: local.Dockerfile
    command: --spring.profiles.active=common,dev
    env_file:
      - ./.env
    environment:
      - VIRTUAL_HOST=cars.delitime.docker
      - VIRTUAL_PORT=8080
    volumes:
      - ./:/var/www
    networks:
      - default

  cars-scheduler:
    container_name: cars.scheduler
    build:
      context: .
      dockerfile: local.Dockerfile
    command: --spring.profiles.active=common,dev,scheduler
    env_file:
      - ./.env
    volumes:
      - ./:/var/www
    networks:
      - default
  
  postgres:
    container_name: postgres
    image: "postgis/postgis:15-3.3"
    ports:
      - 5432:5432
    volumes:
      - ./postgres/data:/var/lib/postgresql/data
      - ./postgres/init:/docker-entrypoint-initdb.d
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
    networks:
      - default

networks:
  default:
    external:
      name: dev-env
```
