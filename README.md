### API `POST /api/main/Categories`
1. Desc: Add a new Category

2. Request param:

		{
		}

3. Sample Request body:

		{
		"Name":"Arts",
		"SubCategories":[
		  {
		     "Name":"Books"
		  },
		  {
		     "Name":"Paintings"
		  },
		  {
		     "Name":"Others"
		  }
		],
		"Type":"MainSection"
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json"
		}

5. Sample Response (id of the insert):

		"53ffebe4fabfdc13843f0881"

7. Additional Info:
	-	The OwnerId is populated by the Controller


### API `Get /api/main/Categories`
1. Desc: Get all Categories

2. Request param:

		{
		}

3. Sample Request body:

		{
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json"
		}

5. Sample Response (id of the insert):

		[
		    {
		        "OwnerId": "a85bcd2a-016b-4d02-b944-492ced86458c",
		        "Name": "Arts",
		        "Type": "MainSection",
		        "SubCategories": [
		            {
		                "OwnerId": null,
		                "Name": "Books",
		                "Type": null,
		                "SubCategories": null,
		                "Id": "54e130d7844d1927e0fd25cd"
		            },
		            {
		                "OwnerId": null,
		                "Name": "Paintings",
		                "Type": null,
		                "SubCategories": null,
		                "Id": "54e130d7844d1927e0fd25ce"
		            },
		            {
		                "OwnerId": null,
		                "Name": "Others",
		                "Type": null,
		                "SubCategories": null,
		                "Id": "54e130d7844d1927e0fd25cf"
		            }
		        ],
		        "Id": "54e130d7844d1927e0fd25cc"
		    }
		]

7. Additional Info:
	-	The OwnerId is populated by the Controller and used for filter

### API `POST /api/main/Classifieds`
1. Desc: Get all published classifieds

2. Request param:

		{
		}

3. Sample Request body:

		{
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json"
		}

5. Sample Response (id of the insert):

		[
		    {
				"ClassifiedDetails": {
					"Type": "Demand",
					"Category": null,
					"Title": "hello 2nd",
					"Description": "hello",
					"Zip": 9100,
					"Price": {
						"AlternativePrice": "By Deal",
						"Price": 11
					}
				},
				"ClassifiedSection": {
					"Section": "Electronics",
					"ExtraSection": [
						"Feature 1(+ Doller 10)"
					],
					"Subcategory": "Phones"
				},
				"Image": {
					"Video": null,
					"Image": []
				},
				"User": {
					"Name": "user",
					"UserId": "b397eeed-2275-4528-90f6-9b65504ebf8f",
					"Email": "user@user.com"
				},
				"IsPublished": false,
				"Id": "54d50305fabfdf05b0a8ba60"
			}
		]

