FORMAT: 1A
HOST: http://localhost:8080/api

# Halo
Software Development Kit (SDK) to access the Halo RESTful API.

## Authentication
This API uses Basic Authentication for its authentication.

# Group Admin

## API Settings By Setting Id [/@/settings/{setting_id}]

+ Parameters
    + setting_id (string, required)


### Get Setting [GET]
Get the fields that constitute the setting

+ Response 200 (application/json)
    + Attributes (array[Setting Field])

### Update Settings [PUT]
Update settings

+ Request (application/json)
    + Attributes (Setting Field)

+ Response 200 (application/json)
    + Attributes (Setting Field)


## API Functions By Function [/@/functions/{function}]

+ Parameters
    + function (enum[string], required)

        The administrative function to be executed

        + Members
            + `update` 
            + `initSectors` 
            + `initAlarms` 
            + `setClock` 
            + `reboot` 


### Execute Function [PUT]
Execute admin function


## API Settings [/@/settings]

### Get Settings [GET]
Get system settings

+ Response 200 (application/json)
    + Attributes (array[Setting])



# Group Message

## Messages By Message Id [/messages/{message_id}]

+ Parameters
    + message_id (string, required)

        The URI path must specify the message ID.


### Get Message [GET]
Get a message. See the Message model for more information.

+ Response 200 (application/json)
    + Attributes (Message)

### Remove Message [DELETE]
Delete a message.  See the Message model for more information.

### Update Message [PUT]
Update a message.  See the Message model for more information.

+ Request (application/json)
    + Attributes (Message)

+ Response 200 (application/json)
    + Attributes (Message)


## Messages [/messages{?page,perPage,fields,sort,id,read,sender,subject,message,tags,categories,createdAt,updatedAt}]

### Get Messages [GET]
Get a collection of messages. See the Message model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + read (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + sender (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + subject (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + message (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + tags (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + categories (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Message])



# Group Team

## Teams [/teams{?page,perPage,fields,sort,id,name,description,permissions,createdAt,updatedAt}]

### Add Team [POST]
Create a team. See the Team model for more information.

+ Request (application/json)
    + Attributes (Team)

+ Response 200 (application/json)
    + Attributes (Team)

### Get Teams [GET]
Get a collection of teams. See the Team model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + permissions (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Team])


## Teams By Team Id [/teams/{team_id}]

+ Parameters
    + team_id (string, required)

        The URI path must specify the team ID.


### Get Team [GET]
Get a team. See the Team model for more information.

+ Response 200 (application/json)
    + Attributes (Team)

### Remove Team [DELETE]
Delete a team. See the Team model for more information.

### Update Team [PUT]
Update a team. See the Team model for more information.

+ Request (application/json)
    + Attributes (Team)

+ Response 200 (application/json)
    + Attributes (Team)


## Projects Teams By Project Id [/projects/{project_id}/teams{?page,perPage,fields,sort,id,name,description,permissions,createdAt,updatedAt}]

+ Parameters
    + project_id (string, required)

        The URI path must specify the parent project ID.


### Get Project Teams [GET]
Get a collection of teams associated with a project. See the Team model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + permissions (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Team])



# Group Property

## Sectors Nodes Properties Property Id [/sectors/{sector_id}/nodes/{node_id}/properties/{property_id}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the parent sector ID.

    + node_id (string, required)

        The URI path must specify the parent node ID.

    + property_id (string, required)

        The URI path must specify the property ID.


### Update Node Property [PUT]
Update a node property.  See the Property model for more information.

+ Request (application/json)
    + Attributes (Property)

+ Response 200 (application/json)
    + Attributes (Property)

### Get Node Property [GET]
Get a node property. See the Property model for more information.

+ Response 200 (application/json)
    + Attributes (Property)


## Sectors Nodes Properties By Sector Id [/sectors/{sector_id}/nodes/{node_id}/properties{?page,perPage,fields,sort,id,type,name,description,unitDisplay,unitDescription,value,maxOperationalValue,minOperationalValue,maxAssignableValue,minAssignableValue,readOnly,sensitivity,silent,maxAlertValue,minAlertValue,alertValue}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the parent sector ID.

    + node_id (string, required)

        The URI path must specify the parent node ID.


### Get Node Properties [GET]
Get a collection of properties for a node. See the Property model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + type (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + unitDisplay (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + unitDescription (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + value (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + maxOperationalValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + minOperationalValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + maxAssignableValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + minAssignableValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + readOnly (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + sensitivity (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + silent (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + maxAlertValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + minAlertValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + alertValue (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Property])



# Group Node

## Sectors Nodes By Sector Id And Node Id [/sectors/{sector_id}/nodes/{node_id}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the parent sector ID.

    + node_id (string, required)

        The URI path must specify the node ID.


### Get Sector Node [GET]
Get a node. See the Node model for more information.

+ Response 200 (application/json)
    + Attributes (Node)

### Update Sector Node [PUT]
Update a node.  See the Node model for more information.

+ Request (application/json)
    + Attributes (Node)

+ Response 200 (application/json)
    + Attributes (Node)

### Remove Sector Node [DELETE]
Create a request to manually uninstall a node.  See the Node model for more information.


## Sectors Nodes By Sector Id [/sectors/{sector_id}/nodes{?page,perPage,fields,sort,id,name,description,type,silent,firmware,status,reachable,installedAt,updatedAt}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the parent sector ID.


### Add Sector Node [POST]
Creates a request to manually install a node into a sector. See the Node model for more information.

+ Request (application/json)
    + Attributes (Node)

+ Response 200 (application/json)
    + Attributes (Node)

### Get Sector Nodes [GET]
Get a collection of nodes. See the Node model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + type (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + silent (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + firmware (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + reachable (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + installedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Node])



# Group Sector

## Sectors [/sectors{?page,perPage,fields,sort,id,name,description,model,addresses,manufacturer,status,silent,engineId,createdAt,updatedAt}]

### Add Sector [POST]
Create a Sector.  See the Sector model for more information.

+ Request (application/json)
    + Attributes (Sector)

+ Response 200 (application/json)
    + Attributes (Sector)

### Get Sectors [GET]
Get a collection of sectors. See the Sector model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

    + name (string, optional)

    + description (string, optional)

    + model (string, optional)

    + addresses (string, optional)

    + manufacturer (string, optional)

    + status (string, optional)

    + silent (string, optional)

    + engineId (string, optional)

    + createdAt (string, optional)

    + updatedAt (string, optional)


+ Response 200 (application/json)
    + Attributes (array[Sector])


## Sectors By Sector Id [/sectors/{sector_id}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the sector ID.


### Get Sector [GET]
Get a Sector. See the Sector model for more information.

+ Response 200 (application/json)
    + Attributes (Sector)

### Remove Sector [DELETE]
Delete a sector. Only owned or authorized sectors can be deleted. See the Sector model for more information.

### Update Sector [PUT]
Update a sector.  See the Sector model for more information.

+ Request (application/json)
    + Attributes (Sector)

+ Response 200 (application/json)
    + Attributes (Sector)


## Projects Sectors By Project Id [/projects/{project_id}/sectors/{sector_id}]

+ Parameters
    + project_id (string, required)

        The URI path must specify the project ID.

    + sector_id (string, required)

        The URI path must specify the sector ID.


### Add Sector to Project [PUT]
Add a sector to a project. Only owned sectors can be added to owned projects. See the Project and Sector models for more information.

+ Response 200 
    + Attributes (string)

### Remove Sector from Project [DELETE]
Remove a sector from a project. Only owned sectors can be removed from owned projects.

+ Response 200 
    + Attributes (string)


## Projects Sectors By Project Id [/projects/{project_id}/sectors{?page,perPage,fields,sort,id,name,description,model,addresses,manufacturer,status,silent,engineId,createdAt,updatedAt}]

+ Parameters
    + project_id (string, required)

        The URI path must specify the project ID.


### Get Project Sectors [GET]
Get a collection of sectors associated with a project. See the Sector model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + model (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + addresses (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + manufacturer (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + silent (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + engineId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Sector])



# Group User

## Users [/users{?page,perPage,fields,sort,id,name,email,bio,company,status,createdAt,updatedAt,admin,username}]

### Add User [POST]
Create a user. See the Person model for more information.

+ Request (application/json)
    + Attributes (Person)

+ Response 200 (application/json)
    + Attributes (Person)

### Get Users [GET]
Get a collection of users. Requests made from administrative accounts return complete person models.  Requests made from non administrative accounts return person models with only the 'username' present. See the Person model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + email (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + bio (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + company (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + admin (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + username (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Person])


## Users By User Id [/users/{user_id}]

+ Parameters
    + user_id (string, required)

        The URI path must specify the person ID.


### Get User [GET]
Get a user. Non administrative requests can only access users liked through a team relationship. See the Person model for more information.

+ Response 200 (application/json)
    + Attributes (Person)

### Remove User [DELETE]
Delete a user. Only administrative requests can delete users. It is not possible to delete the account of the requesting user. See the Person model for more information.

### Update User [PUT]
Update a user. For non administrative requests only self updates are permitted. See the Person model for more information.

+ Request (application/json)
    + Attributes (Person)

+ Response 200 (application/json)
    + Attributes (Person)


## Teams Members By Team Id And User Id [/teams/{team_id}/members/{user_id}]

+ Parameters
    + team_id (string, required)

        The URI path must specify the team ID.

    + user_id (string, required)

        The URI path must specify the person ID.


### Add User to Team [PUT]
Add a user to a team. Only owned teams can add members. See the Person and Team models for more information.

### Remove User from Team [DELETE]
Remove a user from a team. Only owned teams can remove other users. Users can remove themselves from any team they are a member of.


## Teams Members By Team Id [/teams/{team_id}/members{?page,perPage,fields,sort,id,name,email,bio,company,status,createdAt,updatedAt,admin,username}]

+ Parameters
    + team_id (string, required)

        The URI path must specify the parent team ID.


### Get Team Users [GET]
Get a collection of users associated with a team. See the Person model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + email (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + bio (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + company (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + admin (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + username (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Person])



# Group Extension

## Extensions By Extension Id [/extensions/{extension_id}]

+ Parameters
    + extension_id (string, required)

        The URI path must specify the extension ID.


### Get Extension [GET]
Get an extension.  See the Extension model for more information.

+ Response 200 (application/json)
    + Attributes (Extension)

### Remove Extension [DELETE]
Delete an extension. See the Extension model for more information.

### Update Extension [PUT]
Update an extension. See the Extension model for more information.

+ Request (application/json)
    + Attributes (Extension)

+ Response 200 (application/json)
    + Attributes (Extension)


## Extensions [/extensions{?page,perPage,fields,sort}]

### Upload Extension [POST]
Upload an extension. The extension must be in its native format. Do not wrap it in a ZIP or TAR.

+ Response 200 (application/json)
    + Attributes (Extension)

### Get Extensions [GET]
Get a collection of all extensions. See the Extension model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 


+ Response 200 (application/json)
    + Attributes (array[Extension])



# Group Key

## Keys [/keys{?page,perPage,fields,sort,id,publicKey,createdAt,status}]

### Add Access Key [POST]
Create an access key.  See the Access Key model for more information.

+ Response 200 (application/json)
    + Attributes (Access Key)

### Get Access Keys [GET]
Get a collection of all access keys. See the Access Key model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + publicKey (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Access Key])


## Keys By Key Id [/keys/{key_id}]

+ Parameters
    + key_id (string, required)

        The URI path must specify the access key ID.


### Get Access Key [GET]
Get an access key. See the Access Key model for more information.

+ Response 200 (application/json)
    + Attributes (Access Key)

### Remove Access Key [DELETE]
Delete an access key.  See the Access Key model for more information.

### Update Access Key [PUT]
Update access key.  See the Access Key model for more information.

+ Request (application/json)
    + Attributes (Access Key)

+ Response 200 (application/json)
    + Attributes (Access Key)



# Group Project

## Projects [/projects{?page,perPage,fields,sort,id,name,description,createdAt,updatedAt}]

### Add Project [POST]
Create a Project.  See the Project model for more information.

+ Request (application/json)
    + Attributes (Project)

+ Response 200 (application/json)
    + Attributes (Project)

### Get Projects [GET]
Get a collection of projects. See the Project model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Project])


## Projects By Project Id [/projects/{project_id}]

+ Parameters
    + project_id (string, required)

        The URI path must specify the project ID.


### Get Project [GET]
Get a Project. See the Project model for more information.

+ Response 200 (application/json)
    + Attributes (Project)

### Remove Project [DELETE]
Delete a project. Only owned projects can be deleted. See the Project model for more information.

+ Response 200 
    + Attributes (string)

### Update Project [PUT]
Update a project.  See the Project model for more information.

+ Request (application/json)
    + Attributes (Project)

+ Response 200 (application/json)
    + Attributes (Project)


## Sectors Projects By Sector Id [/sectors/{sector_id}/projects{?page,perPage,fields,sort,id,name,description,createdAt,updatedAt}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the parent sector ID.


### Get Sector Projects [GET]
Get a collection of projects associated with a sector. See the Project model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Project])


## Teams Projects By Team Id [/teams/{team_id}/projects{?page,perPage,fields,sort,id,name,description,createdAt,updatedAt}]

+ Parameters
    + team_id (string, required)

        The URI path must specify the parent team ID.


### Get Team Projects [GET]
Get a collection of projects associated with a team. See the Project model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Project])


## Teams Projects By Team Id And Project Id [/teams/{team_id}/projects/{project_id}]

+ Parameters
    + project_id (string, required)

        The URI path must specify the project ID.

    + team_id (string, required)

        The URI path must specify the team ID.


### Add Project to Team [PUT]
Add a project to a team. Only owned projects can be added to owned teams. See the Project and Team models for more information.

### Remove Project from Team [DELETE]
Remove a project from a team. Only owned projects can be removed from owned teams.



# Group Engine

## Engines Nodes By Engine Id [/engines/{engine_id}/nodes]

+ Parameters
    + engine_id (string, required)

        The URI path must specify the parent engine ID.


### Get Engine Nodes [GET]
Get a list of nodes supported by the engine. See the Node model for more information.

+ Response 200 (application/json)
    + Attributes (array[Node])


## Engines Structures By Engine Id [/engines/{engine_id}/structures]

+ Parameters
    + engine_id (string, required)

        The URI path must specify the parent engine ID.


### Get Engine Structures [GET]
Get a list of node hierarchal relationship structures supported by the engine.

+ Response 200 
    + Attributes (object)


## Engines [/engines]

### Get Engines [GET]
Get a list of registered engines. See the Engine model for more information.

+ Response 200 (application/json)
    + Attributes (array[Engine])



# Group Setting

## Extensions Settings By Extension Id [/extensions/{extension_id}/settings/{setting_id}]

+ Parameters
    + extension_id (string, required)

        The URI path must specify the parent extension ID.

    + setting_id (string, required)

        The URI path must specify the parent setting ID.


### Update Extension Setting [PUT]
Update an extension setting field.  See the Setting Field model for more information.

+ Request (application/json)
    + Attributes (Setting Field)

+ Response 200 (application/json)
    + Attributes (Setting Field)

### Get Extension Setting [GET]
Get a collection of fields that make up an extension setting. See the Setting Field model for more information.

+ Response 200 (application/json)
    + Attributes (array[Setting Field])


## Extensions Settings By Extension Id [/extensions/{extension_id}/settings{?page,perPage,fields,sort}]

+ Parameters
    + extension_id (string, required)

        The URI path must specify the extension ID.


### Get Extension Settings [GET]
Get a collection of all settings for an extension. See the Setting model for more information.
+ Parameters
    + page (string, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (string, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 


+ Response 200 (application/json)
    + Attributes (array[Setting])



# Group Dispatch

## Dispatchers [/dispatchers]

### Get Dispatchers [GET]
Get a collection of system dispatchers. See the Dispatcher model for more information.

+ Response 200 (application/json)
    + Attributes (array[Dispatcher])


## Dispatchers Protocols By Dispatcher Id [/dispatchers/{dispatcher_id}/protocols]

+ Parameters
    + dispatcher_id (string, required)

        The URI path must specify the parent dispatcher ID.


### Get Dispatcher Protocols [GET]
Get a collection of all protocols for a dispatcher. See the Dispatcher Protocol model for more information.

+ Response 200 (application/json)
    + Attributes (array[Dispatcher Protocol])



# Group Subscription

## Subscriptions [/subscriptions{?page,perPage,fields,sort,id,name,description,topics,dispatcher,createdAt,updatedAt}]

### Add Subscription [POST]
Create a new Subscription.  See the Subscription model for more information.

+ Request (application/json)
    + Attributes (Subscription)

+ Response 200 (application/json)
    + Attributes (Subscription)

### Get Subscriptions [GET]
Get a collection of subscriptions. See the Subscriptions model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + name (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + description (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + topics (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + dispatcher (string, optional)

        (This is the dispatcher id) Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + createdAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + updatedAt (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Subscription])


## Subscriptions By Subscription Id [/subscriptions/{subscription_id}]

+ Parameters
    + subscription_id (string, required)

        The URI path must specify the subscription ID.


### Get Subscription [GET]
Get a subscription. See the Subscription model for more information.

+ Response 200 (application/json)
    + Attributes (Subscription)

### Remove Subscription [DELETE]
Delete a subscription. See the Subscription model for more information.

+ Response 200 
    + Attributes (string)

### Update Subscription [PUT]
Update a subscription.  See the Subscription model for more information.

+ Request (application/json)
    + Attributes (Subscription)

+ Response 200 (application/json)
    + Attributes (Subscription)



# Group Incident

## Incidents By Incident Id [/incidents/{incident_id}]

+ Parameters
    + incident_id (string, required)

        The URI path must specify the incident ID.


### Get Incident [GET]
Get an incident. See the Incident model for more information.

+ Response 200 (application/json)
    + Attributes (Incident)


## Incidents [/incidents{?page,perPage,fields,sort,from,to,id,silenced,guiltySectorId,guiltyNodeId,guiltyPropertyId,status}]

### Get Incidents [GET]
Get a collection of all incidents. See the Incident model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + from (string, optional)

        The earliest point in time that the results should include. By default this value is set to 10080 mins prior to the time of the request. The value can be specified either as a unix epoch timestamp or in the string format "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"

    + to (string, optional)

        The latest point in time that the results should include. By default this value is set to the time of the request. The value can be specified either as a unix epoch timestamp or in the string format "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"

    + id (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + silenced (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + guiltySectorId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + guiltyNodeId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + guiltyPropertyId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + status (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Incident])



# Group Firmware

## Sectors Nodes Firmwares Firmware Id [/sectors/{sector_id}/nodes/{node_id}/firmwares/{firmware_id}]

+ Parameters
    + sector_id (string, required)

        The URI path must specify the sector ID.

    + node_id (string, required)

        The URI path must specify the node ID.

    + firmware_id (string, required)

        The URI path must specify the firmware ID.


### Update Node Firmware [PUT]
Instruct a hardware node to be updated with a firmware package.


## Firmwares [/firmwares{?page,perPage,fields,sort}]

### Upload Firmware [POST]
Upload new firmware package.

### Get Firmwares [GET]
Get a collection of registered firmware packages. See the Firmware model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 


+ Response 200 (application/json)
    + Attributes (array[Firmware])


## Firmwares By Firmware Id [/firmwares/{firmware_id}]

+ Parameters
    + firmware_id (string, required)

        The URI path must specify the firmware ID.


### Get Firmware [GET]
Get a firmware metadata model. See the Firmware model for more information.

+ Response 200 (application/json)
    + Attributes (Firmware)

### Remove Firmware [DELETE]
Delete a firmware metadata model. See the Firmware model for more information.

+ Response 200 
    + Attributes (string)



# Group Audit

## Audits [/audits{?page,perPage,fields,sort,to,from,action,title,category,actingUserId,targetId,targetType}]

### Get Audits [GET]
Get a collection of system audits. See the Audit model for more information.
+ Parameters
    + page (number, optional)

        Endpoints that return collections are automatically paginated and the first page of results is returned. The desired page number can be targeted using this parameter. e.g. page=2 would return the second page of results.

    + perPage (number, optional)

        Endpoints that return collections are automatically paginated with 10 results per page . The desired number of results per page can be set using this parameter. e.g. perPage=20 would return the 20 results on each page.

    + fields (string, optional)

        It is possible to restrict data models response fields in order to reduce response size. It is possible to specify the fields of the returning model that should be populated with data using a comma separated list of field name. e.g. fields=name,createdAt,updatedAt

    + sort (string, optional)

        The response collection can be sorted into an order based on a specific field value.  The parameter expects a field name from the response model. It is possible to prefix the field name with a minus sign (-) to invert the sort order. e.g. sort=createdAt or sort=-createdAt 

    + to (string, optional)

        The latest point in time that the results should include. By default this value is set to the time of the request. The value can be specified either as a unix epoch timestamp or in the string format "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"

    + from (string, optional)

        The earliest point in time that the results should include. By default this value is set to 10080 mins prior to the time of the request. The value can be specified either as a unix epoch timestamp or in the string format "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"

    + action (enum[string], optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

        + Members
            + `AUTHENTICATED` - Defines a user authentication action using their root credentials. Token and access key authentications do not generate audits.
            + `CREATED` - Defines an action that results in a resource being created.
            + `MODIFIED` - Defines an action that results in a resource being modified.
            + `DELETED` - Defines an action that results in a resource being deleted.
            + `INSTALLED` - Defines node being manually installed.
            + `OTHER` - Defines an other action not defined by the other values specified in this model.

    + title (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + category (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + actingUserId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + targetId (string, optional)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.

    + targetType (string, required)

        Apply a search filter specifically for this model field. The parameter takes a collection of comma separated values that are interpreted  as 'OR' statements. e.g. 'name=foo,baa,lee' will filter the search so that field name must be equal to 'foo' or 'baa' or 'lee'. The query comparator that prefixes the first value can be extended to customise the meaning of the filter condition. Adding an additional '=' creates a 'LIKE' filter instead of 'EQUALS'. e.g. 'name==am' would return all results that  where the model field 'name' is 'LIKE' 'am'. So 'Sam', 'Pam', 'Amber' etc. are valid results. Numerical based fields can use the '>' and '<' to respectively query values that are greater than and smaller than. e.g. 'value=>10' will return only models where the field value is greater than 10. Simple collection fields can use the '^' prefix to indicate a 'CONTAINS' filter. e.g. 'values=^foo' will only return models whether the values field collection contains the value 'foo'.


+ Response 200 (application/json)
    + Attributes (array[Audit])



# Data Structures

## Setting Field (object)
This model represents an HTML field representation.

### Properties
+ `type` (enum, optional) - The HTML input tag type. See the Setting Field Type model for more information.
    + `TEXT`
    + `PASSWORD`
    + `TEL`
    + `URL`
    + `EMAIL`
    + `BOOLEAN`
    + `RADIO`
    + `CHECKBOX`
    + `LIST`
    + `COLOR`
    + `DATE`
    + `DATE_TIME`
    + `TIME`
    + `NUMBER`
    + `RANGE`
+ `name` (string, optional) - Specifies the name of an <input> element.
+ `label` (string, optional) - Specifies the label of an <input> element.
+ `min` (number, optional) - Specifies a minimum value for an <input> element.
+ `max` (number, optional) - Specifies the maximum value for an <input> element.
+ `maxLength` (number, optional) - Specifies the maximum number of characters allowed in an <input> element.
+ `step` (number, optional) - Specifies the legal number intervals for an input field.
+ `pattern` (string, optional) - Specifies a regular expression that an <input> element's value is checked against.
+ `readOnly` (boolean, optional) - Specifies that an input field is read-only.
+ `required` (boolean, optional) - Specifies that an input field must be filled out before submitting the form.
+ `checked` (boolean, optional) - Specifies that an <input> element should be pre-selected when the page loads (for type="checkbox" or type="radio").
+ `value` (string, optional) - Specifies the value of an <input> element.
+ `order` (number, optional) - The order that the field should be displayed in relative to other fields.
+ `options` (array[Setting Field], optional) - For fields that define collections the options for the fields are contained here.


## Person (object)
Each user in Halo is defined as a person.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `name` (string, optional) - The persons real name. e.g. John Doe. Required to create.
+ `email` (string, optional) - The persons email address. This must be unique. Required to create.
+ `bio` (string, optional) - An optional person bio.
+ `company` (string, optional) - An optional company that the person works for or is associated with.
+ `secret` (string, optional) - The users root credential password. This value is never returned. Required to create.
+ `status` (enum, optional) - The status of the persons account determines whether they can use their account or not. See Person State model for more information.
    + `ACTIVE`
    + `PENDING`
    + `SUSPENDED`
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `admin` (boolean, optional) - A boolean flag designating whether the user is a system administrator.
+ `username` (string, optional) - A unique username. This name is available system wide for other users to be able to search for collaborators. Required to create.


## Access Key (object)
When calling Halo APIs, you must authenticate each request using a set of API credentials. Halo associates a set of API credentials with a specific account, and Halo calls these credentials 'Access Keys'. It is strongly recommended that you use  Access Keys for API access and not your accounts root credentials. 

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `publicKey` (string, optional) - The public part of the system generated access key. This is the equivalent of your API username.
+ `privateKey` (string, optional) - The private part of the system generated access key. This is the equivalent of your API password.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `status` (enum, optional) - The status of the access key determines whether the credentials are enabled. See Access Key State model for more information.
    + `ACTIVE`
    + `INACTIVE`


## Message (object)
Messages are the end product of the delivery process from the Halo internal message dispatcher. Subscriptions that implement the Message dispatcher will deliver their broadcasts via messages.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `read` (boolean, optional) - A flag specifying whether the message has been read yet.
+ `sender` (string, optional) - The message sender. If the message originated from an automated process this will be Halo, otherwise the users username is present.
+ `subject` (string, optional) - The message subject.
+ `message` (string, optional) - The actual message.
+ `tags` (array[string], optional) - An optional collection of user defined tags to help search and organise messages.
+ `categories` (array[string], optional) - An optional collection of user defined values to help sort and organise messages.  These are similar to folders in email.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"


## Dispatcher (object)
Halo provides internal hooks that broadcast events on defined 'channels'. Dispatchers provide a dynamic delivery mechanism that will dispatch messages in a specific medium.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. Dispatchers are extension based resources and so this ID does not conform to standard system resource ID formats. This is a 10 character alpha-numeric ID.
+ `name` (string, optional) - A human readable name assigned to the dispatcher.
+ `description` (string, optional) - A human readable description assigned to the dispatcher.


## Dispatcher Protocol (object)
Dispatchers need to define a minimum of 1 protocol. Protocols define the delivery protocols defined by the dispatcher.

### Properties
+ `type` (string, optional) - The type name assigned to the dispatcher protocol.
+ `options` (enum, optional) - An optional collection of the protocol definition options required to make the dispatcher function as a dispatcher. Note that this is the definition not the actual stored value. e.g. An email dispatcher needs the user to define the email addresses that the message should be dispatched to.
    + `TEXT`
    + `PASSWORD`
    + `TEL`
    + `URL`
    + `EMAIL`
    + `BOOLEAN`
    + `RADIO`
    + `CHECKBOX`
    + `LIST`
    + `COLOR`
    + `DATE`
    + `DATE_TIME`
    + `TIME`
    + `NUMBER`
    + `RANGE`


## Engine (object)
Engines are a type of extension that provide Halo support for specific hardware. Engines are generally proprietary extensions provided by the manufacturers to allow Halo support for their internal communication protocols. 

### Properties
+ `manufacturer` (string, optional) - The manufacturer of the hardware that the engine provides support for.
+ `model` (string, optional) - The model of the hardware that the engine provides support for.
+ `description` (string, optional) - A human readable description of the engine.
+ `id` (string, optional) - A unique, system assigned record identifier. Engines are extension based resources and so this ID does not conform to standard system resource ID formats. This is a 10 character alpha-numeric ID.


## Extension (object)
Extension are independent packages that can be installed/removed at runtime by users to extend the core Halo functionality. 

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. Engines are extension based resources and so this ID does not conform to standard system resource ID formats. This is a 10 character alpha-numeric ID.
+ `title` (string, optional) - A human readable title assigned to the extension.
+ `name` (string, optional) - A unique package name assigned to the extension. This is usually a code based workspace assignment.
+ `description` (string, optional) - A human readable description of the extension.
+ `author` (string, optional) - The extension author.
+ `version` (string, optional) - The extension version. Although no format is imposed on extension versions, developers are encouraged to use semantic format.  For more info see http://semver.org/
+ `license` (string, optional) - The type of license that the extension id published under.
+ `frameworks` (string, optional) - A description of the supported core Halo framework versions that are supported by the extension. This takes the format '<comparator><major>.<minor>.<patch>'. e.g. '>=1.0.0'
+ `category` (string, optional) - The category that the extension is categorised under.
+ `homepage` (string, optional) - An optional URL of the extension homepage.
+ `repository` (string, optional) - An optional URL of the extension repository.
+ `status` (enum, optional) - The status of the extension determines whether the extension is enabled. See Extension State model for more information.
    + `ACTIVE`
    + `INACTIVE`
+ `icon` (binary, optional) - An optional Base64 encoded icon.


## Incident (object)
Incidents are similar to conventional alarms. They are time sensitive records that are generated and track the fluctuation of hardware properties that fall outside their standard operational parameters.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `silenced` (boolean, optional) - If any of the system resources from which the incident originated have a silent flag set to true this value will be true. Otherwise it will be false.
+ `guiltySector` (Sector, optional) - The sector that hosts the node or property that was responsible for the incident generation.
+ `guiltyNode` (Node, optional) - The node that was responsible or the node that hosts the property that is responsible for the incident generation.
+ `guiltyProperty` (Property, optional) - The optional property that was responsible for the incident generation.
+ `history` (array[Incident Event], optional) - A collection of historical state changes associated with an incident. See Incident Event for more information.
+ `details` (Incident Detail, optional) - Detailed information pertaining to the incident. See Incident Event for more information.
+ `status` (enum, optional) - The current status of the incident. See Incident State for more information.
    + `GREEN`
    + `YELLOW`
    + `RED`


## Node (object)
Nodes are the fundamental hardware devices that make up a sector. They are the physical or virtual devices that make up a hardware distribution network.

### Properties
+ `index` (string, optional) - The addressable index of the node in the sector network. This should be in a parent -> child  format with the root/head node first followed by a series of progressive child nodes separated  by '>'. e.g. Root > A Child of 'Root' > B Child of 'A Child of Root'. This index is required to install a node manually.
+ `name` (string, optional) - The manufacturer specified name of the node. This is normally an extended version of the device acronym specified as the type.
+ `description` (string, optional) - The manufacturers informational description of the node.
+ `type` (string, optional) - The manufacturer specified typ of the node. This is normally compact acronym version of the specified name.
+ `silent` (boolean, optional) - A flag specifying whether the node should be treated as silent. This flag does not alter any behaviour in the system. It simply propagates its value to incidents that originate from this node. This propagated flag can optionally be included in searches, reporting etc.
+ `firmware` (string, optional) - The firmware version operating on the node.
+ `status` (enum, optional) - The current status of the node. See the Node State model for more information.
    + `GREEN`
    + `YELLOW`
    + `ORANGE`
    + `RED`
+ `reachable` (boolean, optional) - A flag specifying if the node is reachable by Halo.
+ `installedAt` (string, optional) - A timestamp of when the node was installed or registered in Halo. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `extra` (array[Extra], optional) - A collection of custom data that can be bound to the node. See the Extra model for more information.
+ `functions` (array[enum], optional) - A collection of defined functions that apply to this node. This is currently an experimental property. See the Node Function model for more information.
    + `OTHER`
    + `ANTENNA`


## Property (object)
Properties are the variables that make up nodes. These are the readable and writable values.

### Properties
+ `type` (enum, optional) - Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is specified to allow conversion. See the Property Type model for more information.
    + `NUMBER`
    + `PRECISION`
    + `BOOLEAN`
    + `STRING`
+ `name` (string, optional) - A human readable name assigned by the manufacturer to the property.
+ `description` (string, optional) - A human readable descrition assigned by the manufacturer to the property.
+ `unitDisplay` (string, optional) - The units that the property value is measured in.
+ `unitDescription` (string, optional) - A description of the shorthand version of the units.
+ `value` (string, optional) - The actual value of the property. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `maxOperationalValue` (string, optional) - The optional maximum operational value of the property. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `minOperationalValue` (string, optional) - The optional minimum operational value of the property. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `maxAssignableValue` (string, optional) - The optional maximum value that can be assigned to the property if it can have a value assigned to it. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `minAssignableValue` (string, optional) - The optional minimum value that can be assigned to the property if it can have a value assigned to it. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `readOnly` (boolean, optional) - A flag specifying whether the value can only be read or whether it can also be written to.
+ `sensitivity` (number, optional) - Halo uses smoothing algorithms to control the sensitivity of property value interpretation. This sensitivity value must be between 0 and 100. The closer to 100, the more sensitive Halo's interpretation of the true values. The closer to 0 the greater the smoothing effect.
+ `recentValues` (array[string], optional) - A collection of the value over the last 30 mins.  Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `silent` (boolean, optional) - A flag specifying whether the property should be treated as silent. This flag does not alter any behaviour in the system. It simply propagates its value to incidents that originate from this property. This propagated flag can optionally be included in searches, reporting etc.
+ `maxAlertValue` (string, optional) - The optional maximum value that can be reached by the property value before it will instigate an enquiry into the suspect behaviour. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `minAlertValue` (string, optional) - The optional minimum value that can be reached by the property value before it will instigate an enquiry into the suspect behaviour. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `alertValue` (string, optional) - The optional boolean or string value that can be set by the property value before it will instigate an enquiry into the suspect behaviour. Due the way that different languages handle polymorphism and for the convenience of the SDK compatibility all values are represented as String and the actual type is independently specified in the type field.
+ `extra` (array[Extra], optional) - A collection of custom data that can be bound to the property. See the Extra model for more information.
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!


## Sector (object)
Sectors represent a single head end node (with optional multiple failover head nodes) and all the connected downstream nodes.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `name` (string, optional) - A human readable name assigned to the project. Required to create.
+ `description` (string, optional) - An optional human readable description assigned to the project.
+ `model` (string, optional) - The engine model that the sector is hosting. This must match the model specified in the active engine extension exactly. See Engine model for more information.  Required to create.
+ `addresses` (array[string], optional) - A collection of IPv4 or IPv6 addresses (or sockets) for the destination hardware headend  node. The first address in the collection is treated as the primary head end node. All subsequent addresses are treated as failover head end nodes. e.g. 1.1.1.1 or 1.1.1.1:222 or 2001:0db8:0a0b:12f0:0000:0000:0000:0001 or 2001:0db8:0a0b:12f0:0000:0000:0000:0001::80.  Required to create.
+ `proxy` (Proxy, optional) - The optional http(s) proxy server used for connections to the hardware. See Proxy model for more information.
+ `manufacturer` (string, optional) - The engine manufacturer that the sector is hosting. This must match the manufacturer specified in the active engine extension exactly. See Engine model for more information.  Required to create.
+ `status` (enum, optional) - The current status of the sector. See the Sector State model for more information.
    + `ACTIVE`
    + `PASSIVE`
+ `silent` (boolean, optional) - A flag specifying whether the sector should be treated as silent. This flag does not alter any behaviour in the system. It simply propagates its value to incidents that originate from this sector. This propagated flag can optionally be included in searches, reporting etc.
+ `engineId` (string, optional) - The engine ID that the sector is hosting. See Engine model for more information.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `extra` (array[Extra], optional) - A collection of custom data that can be bound to the node. See the Extra model for more information.
+ `owner` (Person, optional) - The project owner. See Person model for more information.


## Subscription (object)
Subscriptions are the binding model that connects system topic broadcasts with dispatchers. A subscription listens for broadcasts of specific topics and passes them to the dispatcher.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `name` (string, optional) - A human readable name assigned to the project. Required to create.
+ `description` (string, optional) - An optional human readable description assigned to the project.
+ `topics` (array[string], optional) - A collection of topics that the subscription should listen for. Required to create.
+ `dispatcher` (string, optional) - The ID of the dispatcher that the broadcast messages should be passed to. Required to create.
+ `protocol` (Dispatcher Protocol, optional) - The dispatcher protocol settings that should be passed to the dispatcher with the broadcast message. See Dispatcher Protocol model for more information.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"


## Team (object)
All system resources in Halo are context sensitive. This means that the creation of a resource results in that resource being owned by the creator. Teams are mechanism of grouping users together and subsequently allowing them to access project resources.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `name` (string, optional) - A human readable name assigned to the project. Required to create.
+ `description` (string, optional) - An optional human readable description assigned to the project.
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `permissions` (array[string], optional) - A collection of permissions assigned to this team. All people who are members of this team will have these permissions when accessing associated project resources. These values can currently be 'create', 'read', 'update' and 'delete'.
+ `owner` (Person, optional) - The team owner. See Person model for more information.


## Incident Detail (object)
Actionable information pertaining to an incident. 

### Properties
+ `name` (string, optional) - A  is a human assignable value for convenience and is not unique.
+ `cause` (string, optional) - A description of the conditions that would cause this alarm definition to become active.
+ `impact` (string, optional) - A description of the impacts that would result in this alarm definition becoming active.
+ `remedy` (string, optional) - A description of the remedy that would resolve this alarm definition if it becomes active.
+ `serviceImpact` (boolean, optional) - A value specifying whether the parent incident is having an impact on the systems service.
+ `cascadingImpact` (boolean, optional) - A value specifying whether the parent incident will have a cascading effect to downstream nodes. .


## Setting (object)
All Halo settings are defined via extensions. This model does not contain the actual settings, instead it is the parent meta model that defines whether settings exist.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. Engines are extension based resources and so this ID does not conform to standard system resource ID formats. This is a 10 character alpha-numeric ID.
+ `extension` (string, optional) - The ID of the extension that the settings belong to.
+ `description` (string, optional) - A human readable description of the extension setting.


## Audit (object)
Whenever a data manipulation transaction is performed, Halo creates a record of the action. You can think of data manipulation transaction as C(reate)U(pdate)D(elete) actions from the CRUD family. These records are called Audits.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!
+ `action` (enum, optional) - The definition of the action that was taken resulting in the creating of the audit. See Audit Action for more information.
    + `AUTHENTICATED`
    + `CREATED`
    + `MODIFIED`
    + `DELETED`
    + `INSTALLED`
    + `OTHER`
+ `title` (string, optional) - A human readable title of the action that was taken resulting in the creating of the audit.
+ `summary` (string, optional) - A short human readable summary of the action that was taken resulting in the creating of the audit.
+ `category` (string, optional) - The category name the resource that the action was taken on resulting in the creating of the audit. e.g. sector
+ `pre` (string, optional) - A string representation of the resource state before the action was performed.
+ `post` (string, optional) - A string representation of the resources state after the action was performed.
+ `actionIp` (string, optional) - The IP address of request that requested the action resulting in the creating of the audit.
+ `actingUserId` (string, optional) - The unique ID of the user that requested the action that was taken resulting in the creating of the audit.
+ `actingUserEmail` (string, optional) - The email of the user that requested the action that was taken resulting in the creating of the audit.
+ `targetId` (string, optional) - The unique ID of the target resource the action was taken on resulting in the creating of the audit.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"


## Extra (object)
'Extra' data provides a way for custom data to be bound to system resources that offer that functionality. In addition to generic custom information Halo provides a collection of reserved keywords that allow predefined functions to be performed. e.g. '@topics' allows custom topics for events to be broadcast on. All reserved keywords start with '@'.

### Properties
+ `key` (string, required) - The key used to define the types of values that are being specified. This can be a free text entry for custom data or it can be a system reserved key starting with '@'.
+ `values` (array[string], required) - A collection of string values assigned to the key. What you specify here depends on the key type and value.


## Incident Event (object)
Being dynamic, incidents are time sensitive and their state fluctuates time. An incident event is a record of state transitions within an incident.

### Properties
+ `time` (string, optional) - A timestamp of when the state transition occured. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `type` (enum, optional) - A definition constant describing the transition event. See Incident Event Type model for more information.
    + `STARTED`
    + `CHANGED`
    + `ENDED`
+ `status` (enum, optional) - The status that the incident state is transitioning to. See Incident State model for more information.
    + `GREEN`
    + `YELLOW`
    + `RED`
+ `details` (string, optional) - A human readable description of what the state transition entailed.


## Project (object)
All system resources in Halo are context sensitive. This means that the creation of a resource results in that resource being owned by the creator. Projects are mechanism of grouping resources together and subsequently allowing teams to access these resources.

### Properties
+ `name` (string, optional) - A human readable name assigned to the project. Required to create.
+ `description` (string, optional) - An optional human readable description assigned to the project.
+ `createdAt` (string, optional) - A timestamp of when the resource was created. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `updatedAt` (string, optional) - A timestamp of when the resource was last updated. The format is: "yyyy-MM-dd'T'HH:mm:ssZ" e.g. "2016-02-14T16:32:47-0500"
+ `owner` (Person, optional) - The project owner. See Person model for more information.
+ `id` (string, optional) - A unique, system assigned record identifier. The ID format is made up as follows: <cluster-id>:<cluster-position> where cluster-id is the id of the cluster. Halo can have a maximum of 32,767 clusters (2^15-1). The cluster-position is the position of the record inside the cluster. Each cluster can handle up to 9,223,372,036,854,780,000 (2^63) records, namely 9,223,372 Trillion of records!


## Proxy (object)
A proxy server is a server that acts as an intermediary for Halo requests. Halo currently only supports HTTP(S) proxy servers.

### Properties
+ `active` (boolean, optional) - A flag defining whether the proxy server should be used.
+ `host` (string, optional) - The URL of the proxy server.
+ `port` (number, optional) - The port that the proxy server is expecting requests on.
+ `authentication` (boolean, optional) - A flag defining whether the proxy server is expecting authentication credentials.
+ `username` (string, optional) - The optional credential username to pass to the proxy server for authentication.
+ `password` (string, optional) - The optional credential password to pass to the proxy server for authentication.


## Firmware (object)
Halo provides the ability to control engine hardware firmware versions. This model is not the actual firmware but rather a representation of the firmware metadata.

### Properties
+ `id` (string, optional) - A unique, system assigned record identifier. Engines are extension based resources and so this ID does not conform to standard system resource ID formats. This is a 10 character alpha-numeric ID.
+ `name` (string, optional) - The firmware package human readable name.
+ `description` (string, optional) - The firmware package human readable description.
+ `manufacturer` (string, optional) - The manufacturer of the hardware supported by the firmware package.
+ `model` (string, optional) - The model of the hardware supported by the firmware package.
+ `nodes` (array[string], optional) - A collection of node types that this firmware is compatible with. These nodes match the node types defined by the engine supporting the target hardware.
+ `version` (string, optional) - The version of the firmware defined in the firmware package .