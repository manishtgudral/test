# Contract Copilot API Documentation

## Table of Contents

Endpoint	Method	Description
/draft/contract/int:id	GET	Retrieves contract information by ID.
/draft/contract	POST	Creates a draft contract.
/draft/contract/int:id	PUT	Updates a contract by its ID.
/draft/contract/int:id	DELETE	Deletes contract by contract ID.
/draft/contracts	GET	Retrieves draft contracts filtered by various params.
/contracts	GET	Retrieves contracts filtered by various params.
/avendra/contract/int:contract_id	DELETE	Deletes contract by contract ID.
/approve-contract/int:contract_id	POST	Approves a draft contract by its ID.
/upload	POST	Uploads a PDF file and extracts data from it.
/draft/products	GET	Retrieves products filtered by various params.
/products	GET	Retrieves products filtered by various params.
/company/int:id	GET	Retrieves company information by ID.
/productions	GET	Retrieves information about all productions.
/companies/contracts	GET	Retrieves all companies with associated contracts.
/companies/draft	GET	Retrieves all draft companies.
/company/draft/int:id	DELETE	Deletes a draft company by its ID.
/company/draft/int:id	PUT	Updates a draft company by its ID.
/company/draft	POST	Creates a draft company.
/product/int:id	GET	Retrieves product information by ID.
/product	POST	Creates a new product.
/product/int:id	PUT	Updates product information by ID.
/product/int:id	DELETE	Deletes a product by its ID.

## API Endpoints

### Get company by ID

- **URL**: `/draft/company/<int:id>`
- **Method**: `GET`
- **Description**: Retrieves company information based on the provided ID.
- **Parameters**:
  - `id`: ID of the company to retrieve.
- **Responses**:
  - `200`: Company information retrieved successfully.
  - `404`: Company not found.
  - `500`: Internal server error.

### Read All Productions

- **URL**: `/productions`
- **Method**: `GET`
- **Description**: Retrieves all productions.
- **Responses**:
  - `200`: Data retrieved successfully.
  - `500`: Error reading data from the database.

### Get all companies with contracts

- **URL**: `/company`
- **Method**: `GET`
- **Description**: Retrieves a list of companies along with their contracts.
- **Parameters**:
  - `production_id` (optional): ID of the production to filter contracts. Defaults to '1' if not provided.
- **Responses**:
  - `200`: List of companies with contracts retrieved successfully.
  - `500`: Internal server error.

### Get all draft companies

- **URL**: `/draft/company`
- **Method**: `GET`
- **Description**: Retrieve all draft companies associated with a production ID.
- **Parameters**:
  - `production_id` (optional): ID of the production to filter contracts. Defaults to '1' if not provided.
- **Responses**:
  - `200`: Successful response.
  - `500`: Internal server error.

### Delete a draft company

- **URL**: `/draft/company/<int:id>`
- **Method**: `DELETE`
- **Description**: Delete a draft company by its ID.
- **Parameters**:
  - `id`: ID of the company to delete.
- **Responses**:
  - `200`: Company deleted successfully.
  - `400`: Bad request.
  - `404`: Company not found.
  - `500`: Internal server error.

### Update a draft company

- **URL**: `/draft/company/<int:id>`
- **Method**: `PUT`
- **Description**: Update a draft company by its ID.
- **Parameters**:
  - `id`: ID of the company to update.
- **Responses**:
  - `200`: Company updated successfully.
  - `400`: Bad request.
  - `404`: Company not found.
  - `500`: Internal server error.

### Create a draft company

- **URL**: `/draft/company`
- **Method**: `POST`
- **Description**: Create a draft company.
- **Responses**:
  - `201`: Company created successfully.
  - `400`: Bad request.
  - `500`: Internal server error.

### Get product by ID

- **URL**: `/draft/product/<int:id>`
- **Method**: `GET`
- **Description**: Retrieve product details by ID.
- **Parameters**:
  - `id`: ID of the product to retrieve.
- **Responses**:
  - `200`: Product details successfully retrieved.
  - `404`: Product not found.
  - `500`: Internal server error.

### Create a new product

- **URL**: `/draft/product`
- **Method**: `POST`
- **Description**: Create a new product and its associated details, colors, and department in the database.
- **Responses**:
  - `200`: Product successfully created.
  - `400`: Bad request.
  - `500`: Internal server error.

### Update product information

- **URL**: `/draft/product/<int:id>`
- **Method**: `PUT`
- **Description**: Update product information by ID.
- **Parameters**:
  - `id`: ID of the product to update.
- **Responses**:
  - `200`: Product successfully updated.
  - `400`: Bad request.
  - `500`: Internal server error.

### Delete a product

- **URL**: `/draft/product/<int:id>`
- **Method**: `DELETE`
- **Description**: Delete a product by its ID.
- **Parameters**:
  - `id`: ID of the product to delete.
- **Responses**:
  - `200`: Product successfully deleted.
  - `400`: Bad request.
  - `404`: Product not found.
  - `500`: Internal server error.

# API Endpoints Documentation

## Read Contract
### GET /draft/contract/<int:id>
Retrieves contract information by ID.

#### Parameters
- id (path parameter): ID of the contract to retrieve. (integer)

#### Responses
- 200: Contract information retrieved successfully.
  - JSON Response Body:
    ```json
    {
        // Contract information
    }
    ```
- 404: Contract not found.
  - JSON Response Body:
    ```json
    {
        "error": "Contract not found"
    }
    ```

## Create Contract
### POST /draft/contract
Creates a draft contract based on the provided data.

#### Request Body
- contract_start_date (string): The start date of the contract. (date format)
- contract_end_date (string): The end date of the contract. (date format)
- client_id (integer): The ID of the client associated with the contract.
- supplier_id (integer): The ID of the supplier associated with the contract.
- version (integer): The version of the contract.
- document_id (integer): ID of the document.
- renewal_date (string): The renewal date for the contract.

#### Responses
- 201: Contract created successfully.
  - JSON Response Body:
    ```json
    {
        "message": "Contract created successfully",
        "id": 123
    }
    ```
- 400: Error creating contract.
  - JSON Response Body:
    ```json
    {
        "error": "Invalid data provided"
    }
    ```
- 500: Internal server error.

## Update Contract
### PUT /draft/contract/<int:id>
Updates a contract by its details.

#### Parameters
- id (path parameter): ID of the contract to update. (integer)

#### Request Body
- contract_start_date (string): The new start date of the contract. (date format)
- contract_end_date (string): The new end date of the contract. (date format)
- client_id (integer): The new ID of the client associated with the contract.
- supplier_id (integer): The new ID of the supplier associated with the contract.
- document_type (string): Type of the document.

#### Responses
- 200: Contract updated successfully.
  - JSON Response Body:
    ```json
    {
        "message": "Contract updated successfully"
    }
    ```
- 404: Contract not found.
  - JSON Response Body:
    ```json
    {
        "error": "Contract not found"
    }
    ```
- 500: Error updating contract.

## Delete Contract
### DELETE /draft/contract/<int:contract_id>
Deletes contract by contract ID.

#### Parameters
- contract_id (path parameter): ID of the contract to delete. (integer)

#### Responses
- 200: Contract deleted successfully.
  - JSON Response Body:
    ```json
    {
        "message": "Contract deleted successfully"
    }
    ```
- 404: Draft contract not found.
  - JSON Response Body:
    ```json
    {
        "error": "Draft contract not found"
    }
    ```
- 400: Error deleting contract.

## Get Draft Contracts
### GET /draft/contracts
Retrieves draft contracts filtered by parameters.

#### Query Parameters
- companyid (integer): ID of the company to filter contracts.
- usertype (string): Type of user to filter contracts.
- agreementtype (string): Type of agreement to filter contracts.
- startdate (date format): Start date to filter contracts.
- enddate (date format): End date to filter contracts.
- production_id (integer): ID of the production to filter contracts. Defaults to '1' if not provided.

#### Responses
- 200: Draft contracts retrieved successfully.
  - JSON Response Body:
    ```json
    {
        "contracts": [
            {
                // Contract details
            }
        ]
    }
    ```
- 500: Error retrieving draft contracts.

## Get Contracts
### GET /contracts
Retrieves contracts filtered by parameters.

#### Query Parameters
- companyid (integer): ID of the company to filter contracts.
- usertype (string): Type of user to filter contracts.
- agreementtype (string): Type of agreement to filter contracts.
- startdate (date format): Start date to filter contracts.
- enddate (date format): End date to filter contracts.
- production_id (integer): ID of the production to filter contracts. Defaults to '1' if not provided.

#### Responses
- 200: Contracts retrieved successfully.
  - JSON Response Body:
    ```json
    {
        "contracts": [
            {
                // Contract details
            }
        ]
    }
    ```
- 500: Error retrieving contracts.

## Delete Contract (Avendra)
### DELETE /avendra/contract/<int:contract_id>
Deletes contract by contract ID.

#### Parameters
- contract_id (path parameter): ID of the contract to delete. (integer)

#### Responses
- 200: Contract deleted successfully.
  - JSON Response Body:
    ```json
    {
        "message": "Contract deleted successfully"
    }
    ```
- 404: Draft contract not found.
  - JSON Response Body:
    ```json
    {
        "error": "Draft contract not found"
    }
    ```
- 400: Error deleting contract.

## Approve Contract
### POST /approve-contract/<int:contract_id>
Approve contract by Contract ID.

#### Parameters
- contract_id (path parameter): ID of the draft contract to approve. (integer)

#### Responses
- 200: Draft contract approved successfully.
  - JSON Response Body:
    ```json
    {
        "message": "Contract approved successfully"
    }
    ```
- 404: Draft contract not found.
  - JSON Response Body:
    ```json
    {
        "error": "Draft contract not found"
    }
    ```
- 500: Error approving contract.

## Upload Files
### POST /upload
Upload a PDF file and extract data from it.

#### Request Body
- file: The PDF file to upload (multipart/form-data)
- type (optional): Type of the document (string)
- version (optional): Version of the document (string)
- production_id (optional): ID of the production (integer)

#### Responses
- 200: Data successfully processed.
- 400: Bad request.
- 500: Internal server error.

## Get All Products
### GET /draft/products
Retrieves products by parameters.

#### Query Parameters
- contract_id (integer): ID of the contract to filter products.
- product_name (string): Product name of product to filter products.
- product_number (string): Product number of product to filter products.
- price_range (string): Price range to filter products.
- production_id (integer): ID of the production to filter products. Defaults to '1' if not provided.

#### Responses
- 200: Products retrieved successfully.
  - JSON Response Body:
    ```json
    {
        "products": [
            {
                // Product details
            }
        ]
    }
    ```
- 500: Error retrieving products.

## Get Products
### GET /products
Retrieves products by parameters.

#### Query Parameters
- contract_id (integer): ID of the contract to filter products.
