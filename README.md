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
