 
** [POST] /api/login**
----
  Login user of given credential .

* **URL Params**  
  None
* **Data Params**  
  {
email : string,
password : string
}

* **Headers**  
  Content-Type: application/json  
* **Success Response:**  
* **Code:** 200  
  **Content:**  
``` 
	{
	data: [{
		data_object,
		Data_object,
		token: string
		...
	}]
	}

```

**[GET] /api/questionnaire**
----
  Returns a client details and questionnaire for a specific client.
* **URL Params**  
  *None
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:** 
* **Code:** 200  
  **Content:** 
  	``` {
	data: [{
		data_object,
		Data_object,
		……
		Questions[{
			Data_object,
			Data_object,
			…

		}]
	}]
	}```

 
 
**[POST] /api/questionnaire/ans**
----
  Save user response of specific questionnaire  
* **URL Params**  
  None
* **Data Params**  
  ```  {
	User_name: string,
	Questionnaire_id: integer,
	User_ans: [{
			Question_id: integer,
			Answer: integer(1 to 7)
		},
		{
			Question_id: integer,
			Answer: integer(1 to 7)
		},
		…
	}]

	}
 ```

* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:**  
* **Code:** 200  
  **Content:**  
```
{
  	 data:  string (success)
}

```
 

**[GET] /api/dashboard**
----
  Get dashboard information like onboard, Roommates Paired, etc.   
* **URL Params**  
  None
* **Headers**  
  Content-Type: application/json 
  Authorization: Bearer `<OAuth Token>`

* **Data Params**  
 None
* **Success Response:**  
* **Code:** 200  
  **Content:**  ```
  {
	data: [{
		Onboarded_users: integer,
		Roommates_pair: integer,
		Last_event_attendence: integer,
		Tenant_attrition: integer,
		Incomplete_onboarding: integer
	}]
}
```

**[GET] /api/tenant/list**
----
  Get a Tenant list.
* **URL Params**  
  None
* **Data Params**  
None
```
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:** 
* **Code:** 200  
  **Content:**  ```
  {
 	data: [{
 		user_name: string,
 		join_on: date(d - m - Y),
 		status: string,
 		…,
 		Compatibility: [{
 			user_name: string,
 			Compatibility: integer,
 			…
 		}]
 	}]
 }
```  
 
**[GET] /api/match/engine**
----
  Get a highest compatible user list, number of user to match on highest score.
* **URL Params**  
  None
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:** 
  * **Code:** 204  
  **Content:** ```
  {
	data: [{
		user_name: string,
		total_match: integer,
		Compatibility: integer,
		match_user_image: string,
		……,

	}]
}
```
**[GET] /api/personality/spectrum**
----
  Get a personality spectrum
* **URL Params**  
  None
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
  Authorization: Bearer `<OAuth Token>`
* **Success Response:** 
  * **Code:** 204  
  **Content:** ```
  {
	data: [{
		the_champion: integer,
		the_healer: integer,
		the_constructor: integer,
		the_instructor: integer,
		the_supporter: integer,
		the_performer: integer,
		the_advisor: integer,
		the_craftsperson: integer,
		night_owl: integer,
		early_riser: integer,
		no_drugs: integer,
		marijuana: integer,
		other_drugs: integer,
		female: integer,
		male: integer,
		Other: integer,
		extrovert: integer,
		……,

	}]
}

```
**[POST] /api/assign**
----
  Assign roommates
* **URL Params**  
  None
* **Data Params**  
  None
  * **Data Params**  
  ```
  {
	User_id: integer,
	assigned_user_id: integer
}
```
* **Headers**  
  Content-Type: application/json  
 * **Success Response:** 
  * **Code:** 204  
  **Content:** ``` 
  {
	data: string(success)
}
 
```
**[POST] /api/manual/match**
----
  List of users for manual match
* **URL Params**  
  None
* **Data Params**  
  None
  * **Data Params**  
  ```
  {
	User_id:integer,
}

```
* **Headers**  
  Content-Type: application/json  
 * **Success Response:** 
  * **Code:** 204  
  **Content:** ``` 
  {
	data: [{
			User_id: integer,
			User_name: string,
			…
		},
		{
			User_id: integer,
			User_name: string,
			…
		}, …
	]
}

 
```
 

