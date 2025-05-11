ENTITIES and Attributes
User
User id:primary key,uuid,indexed
first name:VARCHAR,NOT NULL
last name:VARCHAAR,NOT NULL
email:VARCHAAR,UNIQUE,NOT NULL
password hash:VARCHAAR,NOT NULL
phone number:VARCHAAR,NULL
role:ENUM(guest,host,admin),NOT NULL
created at:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
PROPERTY
property id:Primary Key,UUID,Indexed
host id:Foreign key,references user(user id)
name:VARCHAAR,NOT NULL
description:TEXT,NOT NULL
location:VARCHAAR,NOT NULL
price pernight:DECIMAL,NOT NULL
created at:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
updated at:TIMESTAMP,ON UPDATE CURRENT TIMESTAMP
BOOKING
booking id:primary key,UUID,Indexed
property id:Foreign key,references user(user id)
start date:DATE, NOT NULL
end date:DATE ,NOT NULL
total price:DECIMAL,NOT NULL
status:ENUM(pending,comfirmed,canceled),NOT NULL
created at:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
PAYMENT
payment id:primary key,UUID,Indexed
booking id:Foreign key,references booking(booking id)
amount:DECIMAL,NOT NULL
payment date:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
payment method:ENUM(credit card ,paypal,stripe),NOT NULL
REVIEW
review id:primary key,UUID,Indexed
property id:Foreign key,references property(property id)
user id:Foreign key,references user(user id)
rating:INTEGER,CHECK:rating>=1 AND rating<=5,NOT NULL
comment:TEXT,NOT NULL
created at:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
MESSAGE
message id:primary key,UUID,Indexed
sender id:Foreign key,references user(user id)
recipient id:Foreign key,reference user(user id)
message body:TEXT,NOT NULL
sent at:TIMESTAMP,DEFAULT CURRENT TIMESTAMP
Constraints
USER TABLE
unique constraint on email.
non-null contraints on required fields
PROPERTY TABLE
foreign key contraint on host id
non-null contraints on essentials attributes.
BOOKING TABLE
FOREIGN KEY constraints on property id and user id.
status must be one of pending,confirmed,or canceled
PAYMENT TABLE
foreign key constraint on booking id,ensuring payment is linkined to valid bookings
REVIEW TABLE
contraints on rating values(1-5)
foreign key constraints on property id and user id
MESSAGE TABLE
foreign key constraints on sender id and recipient id
INDEXING
primary keys:indexed automatically
additional indexes:email in the user table,property id in the property and bookingtables,booking id in the booking and payment table
