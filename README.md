# College-assignments

# REAL ESTATE WEBSITE 
# Teaching Program Microservice

**Example:**
```markdown

Schema:
Program: (id, title, description, prerequisite) 
PROPERTIES: (id, propertyId, title, short_description)

## API Endpoints:
Program Management


POST /programs/create: Creates a new property.
PUT /programs/{programId}/update: Updates a property details.
DELETE /programs/{programId}/delete: Deletes a program.
GET /programs/list: Retrieves a list of all properties.

## API : Get All PROPERTIES
Endpoint: api.property.com/program/all
Method: GET
Description: Retrieves a list of all properties available in the system.
Request:
No request body is required for this API as it retrieves all properties.

Successful Response:

{
    "status": "success",
    "programs": [
        {
            "ProgramId": "P001",
            "Title": "PROPERTY DETAIlS",
            "Description": "Showing all details of property to user"
            "Prerequisites": "None"
        },
        {
            "ProgramId": "P002",
            "Title": "Further Process of sell & Buy",
            "Description": "An  focused on applied Generative AI techniques.",
            "Prerequisites": "None"
        }
    ]
}

Failed Response:
{
    "status": "error",
    "message": "No programs currently available."
}


## API : Get Specific State property
Endpoint: api.property.com/program/{id}
Method: GET
Description: Retrieves details about a specific state proeperty.
Request:
{ 
    "propertyID": "P001"
}
Successful Response:
{
    "status": "success",
    "PropertyId": "P001",
    "Title": "Property details for ohio state property",
    "Description": "A comprehensive details covering all properties of ohio state.",
    "ShortDescription": "A comprehensive details covering all properties of ohio state in united states .",
    "Prerequisites": "None",
    "Courses": [
        {
            "CourseId": "C001",
            "Title": "comarcial properties",
            "Description": "This the list of all comercial propertie in the ohio",
            "ShortDescription": "comarcial properties/shops/industrial areas"
        },
        {
            "CourseId": "C002",
            "Title": "residencial properties",
            "Description": "This course covers cloud-native concepts and practices.",
            "ShortDescription": "residencial properties/lands/plots"
        }
    ]
}
Failed Response:
{
    "status": "error",
    "message": "Property not found for the provided propertyID."



    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}
API : Update Program
Endpoint: api.property.com/program/update/{id}
Method: PUT
Descr## API : Create New Property
Endpoint: api.Property.com/program/create
Method: POST
Description: Creates a new Property with the specified details.
Request:
{
    "title": "new property",
    "description": "Cover all subdivisions of properties.",
    "prerequisite": "None"
}

Successful Response:
{
    "status": "success",
    "ProgramId": "P003",
    "message": "property created successfully."
}
Failed Response:
{iption: Updates the details of an existing propert identified by its id.
Request:
{
    "id": "P001"
}
{
    "title": "Florida state Properties",
    "description": "FLorida states propertiesa are good investment",
    "prerequisite": "hoa fees"
}
Successful Response:
{
    "status": "success",
    "program": {
        "id": "P001",
        "title": "florida state properties",
        "description": "FLorida states propertiesa are good investment",
        "prerequisite": "hoa fees"
    },
    "message": "Program updated successfully."
}
Failed Response: (Not Found )
{
    "status": "error",
    "message": "property not found for the provided ID."
}
Failed Response: (Invalid Input )
{
    "status": "error",
    "message": "Invalid input data. Please check the required fields."
}

## API :  Delete Program
Endpoint: api.panaversity.com/program/delete/{id}
Method: DELETE
Description:Deletes an existing program identified by its id.
Request:
No request body needed; Id is passed as a URL parameter
Successful Response:
{
    "status": "success",
    "message": "Program deleted successfully."
}
Failed Response:
{
    "status": "error",
    "message": "Program not found for the provided ID."
}


