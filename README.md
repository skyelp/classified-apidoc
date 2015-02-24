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
		    
		
7. Additional Info:


### API `GET /api/main/MyClassifieds`
1. Desc: GET my classifieds

2. Request param:

		{
			type : String // type = null or 'all' return all user classifieds, type = 'published' return all published classifieds,
						  // type = 'saved' return all saved classifieds	
		}

3. Sample Request body:

		{
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

### API `GET /api/main/Classifieds/Image`
1. Desc: GET a blob image url
 
2. Request param:

		{
		}

3. Sample Request body:

		{
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json",
			Authorization : "Bearer String" // Access token is required for this request
		}

5. Sample Response :

		{
			"sasUrl": "https://skydocs.blob.core.windows.net/image/c11424e0-bc8a-43c3-9366-eebdead02a45.jpg?sv=2014-02-14&sr=c&sig=3friG15l8G2MMeALz9al%2FcoepMwkH7xFUhTFxQ0i0X8%3D&st=2015-02-23T13%3A13%3A30Z&se=2015-02-23T13%3A28%3A30Z&sp=w",
			"imageUrl": "http://skydocs.blob.core.windows.net/image/c11424e0-bc8a-43c3-9366-eebdead02a45.jpg"
		}   
		
7. Additional Info:

### API `GET /api/main/Classifieds/MainSection`
1. Desc: GET date for classifieds section in addClassified
 
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

5. Sample Response :

		{
			"Section": [
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
			],
			"ExtraSection": [
				{
					"Name": "Feature 2",
					"Currency": "Euro",
					"Price": {
						"AlternativePrice": null,
						"Price": 10
					},
					"Id": "540b279ffabfdc67cce77a61"
				}
			]
		}  
		
7. Additional Info:

### API `POST /api/main/sendmail`
1. Desc: GET date for classifieds section in addClassified
 
2. Request param:

		{
		}

3. Sample Request body:

		{
			MailBody : string,
			MailSubject : string,
			ToAddress : {
				Name : string,
				MailAddress : string
			}
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json",
			Authorization : "Bearer String" // Access token is required for this request
		}

5. Sample Response :

		{
			Success : boolean
		}
		
7. Additional Info:

### API `POST /api/main/Payment`
1. Desc: payment 
 
2. Request param:

		{
		}

3. Sample Request body:

		{
			FirstName : string,
			LastName : string,
			UserId : string,
			Address : string,
			State : string,
			Zip : string,
			CardNumber : string, // Required
			Expiry : string, // Required
			Amount : string, // Required
			Description : string
		}

4. Request headers:

		{
			Content-Type : "application/json",
			Accept : "application/json",
			Authorization : "Bearer String" // Access token is required for this request
		}

5. Sample Response :

		{
			Success : boolean
		}
		
7. Additional Info: