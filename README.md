# Unemployment_Certify_Reminder
Automation that reminds you to certify for unemployment benefits

1. Create a Make Account
2. Create a Scenario

Gmail Module: 

1. Right click on the workspace interface and click "Add Module"
2. Connect your Gmail
3. Click on "Make an Api Call" out of all the options avaliable.
   Make sure all the following features are selected
   
  a. Method = GET
  
  b. Key (Header 1) : Content Type
  
  c. Value (Header 1): application/json
  
  d. Key: q
  
  e. value: subject:"[Payment Approved: {{formatDate(addDays(setDay(now; "sunday"); -7); "MMMM D"; "America/New_York")}}-{{if(formatDate(addDays(setDay(now; "sunday"); -7); "MMMM"; "America/New_York") = formatDate(addDays(setDay(now; "saturday"); -7); "MMMM"; "America/New_York"); formatDate(addDays(setDay(now; "saturday"); -7); "D"; "America/New_York"); formatDate(addDays(setDay(now; "saturday"); -7); "MMMM D"; "America/New_York"))}}] NJ Unemployment Insurance Weekly Claim"

* For part e. you are letting Make know to recognize the email that is sent to your inbox after you certify for benefits.  For this, you may need to change parts like "Payment Approved", and "NJ Unemployment Insurance Claim".  If you need help, ask any ai service on how to format this formula. Tell the ai what your email subject looks like.* 

If - Then Modula: 
1. In the workspace, click the "+" connector of the Gmail Modula
2. Select the *IF-ELSE* Module
3. For the top most module which satsifies the IF condition, then click on Send Email, and write an alert email that lets you know that there is no need to certifiy. 
4. For the bottom most module which satsifies the ELSE condition, click on Send Email, and write an alert email that reminds you to recertify. 



