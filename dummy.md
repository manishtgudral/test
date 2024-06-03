# Contract Copilot API Documentation

## Table of Contents

- [Get company by ID](#get-company-by-id)
- [Read All Productions](#read-all-productions)
- [Get all companies with contracts](#get-all-companies-with-contracts)
- [Get all draft companies](#get-all-draft-companies)
- [Delete a draft company](#delete-a-draft-company)
- [Update a draft company](#update-a-draft-company)
- [Create a draft company](#create-a-draft-company)
- [Get product by ID](#get-product-by-id)
- [Create a new product](#create-a-new-product)
- [Update product information](#update-product-information)
- [Delete a product](#delete-a-product)

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
