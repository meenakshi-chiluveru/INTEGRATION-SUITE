**Day 11 – Router Configuration in CPI**

As we dive deeper into the integration process, let’s explore the essential SAP error status codes that commonly arise when dealing with HTTP requests:

- **400 – Bad Request:** This error indicates that the server could not understand the request due to invalid or incorrectly formatted data being sent.
- **401 – Unauthorized:** This signifies that the request requires user authentication, and the provided credentials are either missing or incorrect.
- **404 – Not Found:** This error shows that the requested resource could not be located on the server.
- **500 – Internal Server Error:** This is a catch-all error indicating that there is a problem on the server side while processing the request.
- **503 – Service Unavailable:** This indicates that the server is currently unable to handle the request due to temporary overload or maintenance.
- **200 – OK:** This confirms that the request has been successfully processed without any issues.
- **202 – Accepted:** This means that the request has been accepted for processing, but the processing has not been completed yet. However, the status of the data is uncertain at this point.

To monitor errors on the source side, such as when using Postman, you can navigate to the blank space of the iFlow, access the error configuration, and check the option to return exceptions to the sender.

### Conditional Data Routing in CPI

In the context of Cloud Platform Integration (CPI), if you need to send data from a source to multiple receivers based on specific conditions, you can utilize a powerful feature known as conditional-based routing. 

For instance, imagine you have two email receivers. To facilitate this routing:

1. **Utilize the Router Palette:** Begin by dragging a router element from the palette into your iFlow setup.
2. **Define Multiple Routes:** You will need two distinct paths for your two applications. To establish the second route, you simply add a second end message.
3. **Branching Logic:** Connect one branch from the router to the second end message, allowing each path to be clearly defined.
4. **Configuration of Conditions:** You can maintain conditions in either XML or non-XML formats, ensuring that the data type remains consistent across both branches.

### Implementing Routing Logic

When it comes to specifying routing conditions:

- For the receiver configuration, utilize XPath to define the criteria. 
- It is crucial to establish a default path to handle any data that doesn't meet the specified conditions. 
- If you are dealing with multiple adapters of the same type, you can conveniently copy configurations to maintain consistency.

Once your configuration is complete, deploy the iFlow. For testing, you can send data from Postman that relates to either India or England. Remember to enable tracing to monitor the flow of data closely.

When a condition is set properly, data will seamlessly route to the specified application. Any data deemed irrelevant or not matching the conditions will automatically redirect to the default branch. 

It is critical to always include a default branch in every router setup to avoid potential data loss. 

You can maintain as many routes as necessary within your router. For example, a condition could be defined as:

```xpath
//SHIPCOUNTRY = ‘ENG’
```

For non-XML data, you will need to provide appropriate headers and properties, such as `${HEADER.HEADERNAME} = ‘ENG’`. To manage this, you can create headers and properties using the content modifier within the iFlow and specify the XPath in the message header. 

For non-XML conditions, the expressions must be clearly articulated to ensure accurate routing. This structured approach ensures that your data flow in CPI remains efficient and well-organized.








