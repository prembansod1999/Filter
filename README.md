# Filter
1. Filter is an object that is invoked at preprocessing and postprocessing of the request.
2. It is Executed before and after servlet execution.
3. It is plugable. i.e. its entry is present in the web.xml file and we can plug in and plug out by adding or removing the filter entry from the web.xml file. without any change in the servlet.

---------------------------------------------------------------------------------------------

Usage of Filter:

1. Authentication and authorization of request for resource.
2. formatting of request body or header before sending it to the servlet.
3. compressing the response data send to the client.
4. While sending response we can add cookies, header information etc.
5. input validation etc.

---------------------------------------------------------------------------------------------

Filter API

1. Filter interface used to implement Filter.
2. FilterChain interface is used to forward request to the next resource or next servlet.
3. FilterConfig interface is used to get data from web.xml or external resource during initilization of the filter.


1. Filter interface contains below methods:

1. init() it is used at the time of object initialization.
2. doFilter() It is executed for preprocessing and processing.
3. destroy() it is used at the time of object destruction.

All these three interfaces i.e. Filter, FilterChain, FilterConfig are present in the javax.servlet package.


---------------------------------------------------------------------------------------------

doFilter of the FilterChain is used to seprate the preprocessing and postprocessing logic:

Ex:

FilterChain chain;

System.out.println("This is executed preprocessing");

chain.doFilter();

System.out.println("This is executed postprocessing");

---------------------------------------------------------------------------------------------

Filter is need to be configured and filter mapping needs to be added in the web.xml file it is same as servlet as follows:

<filter>
	<filter-name>filter1</filter-name>
	<filter-class>packagename.Classname</filter-class>
</filter>

<filter-mapping>
	<filter-name>filter1</filter-name>
	<url-pattern>Provide name of the servlet on which filter needs to be apply</url-pattern>
</filter-mapping>

To apply filter on  all url provide like below

	<url-pattern>/*</url-pattern>

To apply on multiple servlet provide like below:

<filter-mapping>
	<filter-name>filter1</filter-name>
	<url-pattern>/Servlet1</url-pattern>
	<url-pattern>/Servlet2</url-pattern>
</filter-mapping>


---------------------------------------------------------------------------------------------







