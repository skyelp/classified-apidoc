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
