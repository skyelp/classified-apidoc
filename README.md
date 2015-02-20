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

### API `GET /api/main/Classifieds`
1. Desc: Get published classifieds

2. Request param:

		{
			// if null, return all
			id : 'optional, id of the classifeds, return matched classifed',
			category : 'optional, category name of classifeds, filter classifeds using category',
			subcategory : 'optional, subcategory name of classifieds, filter classifieds using subcategory',
			page : 'optional, for pagination, return 8 classifieds per page'
		}

3. Sample Request body:

		{
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json"
		}

5. Sample Response :

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
7. Additional Info:

### API `POST /api/main/Classifieds`
1. Desc: POST classifieds

2. Request param:

		{
		}

3. Sample Request body:

		{
			ClassifiedDetails : {
				type : String,
				category : String,
				Titile : String,
				Description : String,
				Zip : int,
				Price : {
					AlternativePrice : String,
					Price : int
				}
			},
			ClassifiedSection : {
				Section : String,
				Subcategory : String,
				ExtraSection : [] //List of String
			},
			ImageEntity : {
				Video : String,
				Image : [] //List of String 
			},
			User : null, // Will be filled by server
			IsPublished : null // Will be filled by server
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json",
			Authorization : "Bearer String" // Access token is required for this request
		}

5. Sample Response :

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
7. Additional Info:
