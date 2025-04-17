Day 11 – router
https sap error status codes
400 – bad request – we are sending incorrect data
401 – unauthorised
404 – resource does not exist
500 – internal server error – message processing issue at target end
503 – server is down
200 -ok -success
202- accepted data -not sure about data
To see error in source side like postman -click on blank space of iflow – error config – checkmark on return exception to sender
 
 
The above is error shown in postman


 
How to send data from sorce to receiver based on condition which was given in cpi
in cpi we have one pallete option when there are multiple receivers that conditional based routing
ex:
take two receivers like mails reveivers
 

To do routing we have pallete option in cpi like above showing
Take one router pallete
We need two routes for two applications 
In order to add second route we need to add second end message
Take one branch from router to end 2nd
Condition can maintain in xml or non-xml
Should maintain same datatype in both branches
 

 
We shoud give xpath for receiver
And maintain one default path
If there are multiple same adaptors we can copy configuration one other
Deploy the iflow
Have to send data from postman either india or England related
Enable trace
Select xml data in source applicatin 
If we maintain one condition data will flow to that app apart from if ny data irrivelent that will route to default branch
In every router default branch should be compulsory
We can maintain n number of routes to our router
WE CAN MAINTAIN CONDITION LIKE - //SHIPCOUNTRY = ‘ENG’
IF WE GIVE NON-XML DATA WE SHOUD GIVE HEADER AND PROPERTY- ${HEADER.HEADERNAME} = ‘ENG’
WE HAVE TO CREATE HEADER AND PROPERTY FOR ROUTE BY USING CONTENT MODIFIER
GIVE XPTH IN MESSAGE HEADER
NON-XML CONDITION SHOULD BE IN EXPRESSION








