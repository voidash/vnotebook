# entity

TODO : notification module
 admin dashboard features:
 images, for carousel,
 logo should be settable by admin panel


every category must have images

ask for asset files

## Database Requirements

### components/packages

* User accounts 
    * For storing login ID, password, address, profiles, usage history etc
 * Product
     * Actual product with appropriate attributes
 * Catalog
     * For categorizing items by Brand(so it contains attributes associated with brands)
 * Cart
     * Product with quantity and other attributes 
 * Order
     * Method of shipment, discounts, method of payment
 * Logistics
     * after order is confirmed, handling of shipment

### Entity-Attribute relation(crude)

#### Category
* Category_id
* Category_name
* CategoryIsBrand
* FallsUnderPrimary(wear, electronics) 
* FallsUnderSecondary(footwear/shoes,laptop)


#### Products
 
 * Product_item_no #
 * Product Quantity
 * Weight and dimensions (because of shipping issues)
 * Title
 * Discount Factor 
 * category (foreign key)
 * Price
 * Rating
 * Date Added
 * Description
 * Discount codes default = NULL
 * Images
 * Video nullable 
 * Vendor (foreign key)
 * Comments (foreign key)
 * messages( foreign key)
 
 
#### Discount
* Discount_id#
* Quanitity
* Percent

#### Cart

* cart_id#
* product_id (foreign key)
* product quantity
* user_id (foreign key)
* ordered?

#### Messages
 
 * message_key #
 * Recipient (foreign key)
 * By (foreign key)
 * Product (foreign key)
 * Description
 * Read? 
 * Reply To ( foreign key that will contain message_key)


#### Inquiry
* inquiry_id#
* Product_id( foreign key)
* Desritption
* Attachment (BLOB)


#### Users

* unique_id#
* Name (fname and lname)
* email
* password
* cover image
* profile image
* Roles (foreign key)
* contact Number
* address
* Items ordered history (foreign key), one to many field


#### Roles
* Role id
* Role name
* Role Permission (foreign key)

#### Role Permission
* Permission id#
* Permission name

#### Order
* cart id# (foreign key) (one to one)
* Shipped?
* transaction_method(foreign key)
* Amount( maybe required for API of khalti)
* Full Name
* mobile Number
* District 
* City
* Area
* Address (detailedOne)

#### Vendor Detail
* user_id # (one to  one) foreign key
* Company Name
*  Company Address
* Company Description
* Established Date
* product categories ( one to many ) ( foreign key)
* Province
* City
* Postal Code
* Employees
* Website
* ISO
* TM
* PAN
* VAT
* Process Control

#### RequestProduct
* Request_id
* Product Name
* Quantity
* Price
* Shipping Address
* Payment_method(foreign key)


#### Transaction method
* transaction_method_id#
* name


#### Address
*

#### Comments
* comment_id#
* profile_id (fk)
* description
* product_id (fk)
* Parent(fk to itself store comment_id)

