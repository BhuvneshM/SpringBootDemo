# SpringSecurityLoginTutorial

1. mvn clean
2. mvn clean install
3. Go to the target folder
4. java -jar demo-0.0.1-SNAPSHOT.ja

- http://localhost:8080/registration (bydefault)
- http://localhost:9090/login

//https://medium.com/@gustavo.ponce.ch/spring-boot-spring-mvc-spring-security-mysql-a5d8545d837d

http://localhost:9090/bookingapi/bookingCab (add bookingdetails)
{
   "customerName":"Sreenivas Muniganti",
   "startlocation":"Pune",
   "destinationLoc":"Shiridi",
   "ratePerKilometer":"10",
   "journeyDate":"10-08-2018",
   "customerMobileNumber":"8308606312",
   "advanceAmount":"1000"
}
---------------------------------------------------------------------
http://localhost:9090/apiVehicle/postVehicle (add new vehicle)
{
    "vehicleId": 1,
    "vehicleNumber": "MH12F1234",
    "vehicleStatus": "NotScheduled",
    "vehicleType": "XUV",
    "createdAt": "2018-08-20T17:12:23.503+0000",
    "updatedAt": "2018-08-20T17:12:23.503+0000"
}
--------------------------------------------------------------------
http://localhost:9090/apiDriver/addDriver (add new Driver)
{
   "driverId":"101",
   "driverName":"MH12F1234",
   "driverLicenceNum":"NotScheduled",
   "driverStatus":"XUV"
}
----------------------------------------------------
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
http://localhost:9090/orderdetails/saveOrder
{
   "bookingId":"42",
   "totalAmount":"10000",
   "advanceAmount":"1000",
   "customerName":"PankajM",
   "startlocation":"Pune",
   "destinationLoc":"Jodhpur",
   "totalRide":"1100",
   "ratePerKilometer":"10",
   "customerMobileNumber":"8308606312"
}


Select v.vid, v.vName, b.sDate, b.eDate from vehicle v, Booking b where v.vid =b.vid and 

//https://www.youtube.com/watch?v=qYTSCi6bh00  (mapping)


CREATE TABLE Vehicle
( supplier_id numeric(10) not null,
  supplier_name varchar2(50) not null,
  contact_name varchar2(50),
  CONSTRAINT supplier_pk PRIMARY KEY (supplier_id)
);

CREATE TABLE Driver
( supplier_id numeric(10) not null,
  supplier_name varchar2(50) not null,
  contact_name varchar2(50),
  CONSTRAINT supplier_pk PRIMARY KEY (supplier_id)
);


CREATE TABLE BookingCab
( product_id numeric(10) not null,
  supplier_id numeric(10) not null,
  CONSTRAINT fk_supplier
    FOREIGN KEY (supplier_id)
    REFERENCES supplier(supplier_id)
);
====================================================================


CREATE TABLE Vehicle
( VEHICLE_ID numeric(10) not null,
  VEHICLE_STATUS varchar2(50) not null,
  VEHICLE_TYPE varchar2(50),
  VEHICLE_NUMBER varchar2(50),
  CREATED_AT TIMESTAMP(6),
  UPDATED_AT TIMESTAMP(6),
  CONSTRAINT Vehicle_pk PRIMARY KEY (VEHICLE_ID)
);

CREATE TABLE Driver
( DRIVER_ID numeric(10) not null,
  DRIVER_LICENCE_NUM varchar2(50) not null,
  DRIVER_NAME varchar2(50),
  DRIVER_STATUS varchar2(50),
  CONSTRAINT Driver_pk PRIMARY KEY (DRIVER_ID)
);


CREATE TABLE Booking_Details
( BOOKING_ID numeric(10) not null,
  DRIVER_ID numeric(10) not null,
  ADVANCE_AMOUNT varchar2(50),
  CUSTOMER_MOBILE_NUMBER varchar2(50),
  CUSTOMER_NAME varchar2(50),
  DESTINATION_LOC varchar2(50),
  RATE_PER_KILOMETER varchar2(50),
  STARTLOCATION varchar2(50),
  CREATED_AT TIMESTAMP(6),
  JOURNEY_DATE TIMESTAMP(6),
  UPDATED_AT TIMESTAMP(6),
  CONSTRAINT fk_Driver
    FOREIGN KEY (DRIVER_ID)
    REFERENCES Driver(DRIVER_ID)
);



https://stackoverflow.com/questions/13154818/how-to-define-a-jpa-repository-query-with-a-join
IMP::::::::::::::::::
https://github.com/gustavoponce7/SpringSecurityLoginTutorial/tree/master/src/main/resources
https://medium.com/@gustavo.ponce.ch/spring-boot-spring-mvc-spring-security-mysql-a5d8545d837d
