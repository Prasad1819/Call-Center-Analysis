# Call Center Analysis

## Problem Statement

This dashboard helps the Call Center to understand their customers better. It helps the Call Center to know if their customers are satisfied with their services. Through different ratings, they get to know their improvement area, & thus they can improve their services by identifying these area. It also lets them know the calls by date ,calls by state,total calls by call center, thus since by using this dashboard they have identified this problem, they can further work on factors responsible for there other issues.

### Dashboard 1 : HOME
KPI'S Requirement

1. Total Number of calls : We need to track and display the total number of calls recieved by our call center over a specified period.

2. Total Call Duration in Hours : It is crucial to understand the total amount of time our call center staff spends on calls in hours , which can help us in resouce allocation and capacity planning.

3. Total Call Duration in Minutes : Similar to the total call duration in hours , this KPI provide the total call time but in minutes , offering a more granular view of call durations. 

4. Average Call Duration in Minutes : To assess the effieciency of our agents, we need to calculate and display the average call duration in minutes . This metric can help identify trends in call handling.

5. Response Time Percentage : Response time is critical factor in customer satisfaction . This KPI should display the percentage of calls answered within a predefined time frame , helping us guage our ability to provide prompt service.

### Dashboard 2 : GRID

* Create a Grid view dashboard displaying a table of call details in Power Bi .
* This should allow user to export the grid for various filters applied.


For Creating new Columns following DAX expression was written;
       
        Date Table = CALENDAR(MIN('Call Center_Call Center'[Call Timestamp]),MAX('Call Center_Call Center'[Call Timestamp]))
        
        Day = FORMAT('Date Table'[Date], "ddd")
        
        Day No = WEEKDAY('Date Table'[Date],1)
        

For Creating new measures following DAX expression was written;
       
        Total Calls = COUNT('Call Center_Call Center'[Id])
        
        Total Call Duration (min) = SUM('Call Center_Call Center'[Call Duration In Minutes])
        
        Total Call Duration (Hrs) = [Total Call Duration (min)]/60
        
        Avg Call Duration (min) = AVERAGE('Call Center_Call Center'[Call Duration In Minutes])

        Response Time % = CALCULATE([Total Calls],'Call Center_Call Center'[Response Time] = "Within SLA" || 'Call Center_Call Center'[Response Time] = "Above SLA") / [Total Calls]

         
  The report was then published to Power BI Service.
 
 
![Publish_Message](https://user-images.githubusercontent.com/102996550/174094520-3a845196-97e6-4d44-8760-34a64abc3e77.jpg)

# Snapshot of Dashboard (Power BI Service)

### HOME

![Call center HOME](https://github.com/Prasad1819/Call-Center-Analysis/assets/135447940/60183b9e-06b5-4209-8857-898637df0567)

 ### GRID 
![call center GRID](https://github.com/Prasad1819/Call-Center-Analysis/assets/135447940/ade03456-888d-4914-a8ef-a1f41af7ee76)


 
