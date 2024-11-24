# Salesforce Developer Interview Querstions for 2 year Experienced:
## NOTE: this questions list i made based on the around 7 interviews i given.

**SOQL:**

1. Write a query that returns the Account Name and its related Opportunity count.
2. Write a query that returns the second-highest Opportunity with its amount.
3. Write a query that fetches Accounts and their related Contacts count.
4. Write a query to fetch Opportunities related to Accounts.
5. I want to query custom object data that respects org settings.

**APEX:**

1. Write an Apex class that returns Account data to an LWC so that we can call it using an imperative call.
2. Write an Apex method for outbound data transfer.
3. Write an Apex method that receives inbound data and stores it in an object.
4. Write an Apex class that calls an external API.
5. Write an Apex method that creates five Account records.
6. Can we call the Apex class from a Flow? How?
7. What is "with sharing" and "without sharing"?
8. Can we insert an Account, related Contact, and related User in one class? If not, why?
9. What annotation is used when we need to pass data to an LWC?
10. What are the different types of context variables in triggers?
11. When do we use List, Map, and Set in Salesforce?
12. When do we use triggers over Flows?
13. How do we secure API credentials and access in Apex?

**Scenario-Based Apex:**

1. **Scenario:** My org has 200 records, but when I return data using the below call, I’m getting only 20 records. What is the issue in my class? Why does it return only 20 records?

```apex
public class FetchData {
  
   public Map<Datetime, Account> returnAccountData() {
     List<Account> accList = [Select Id, Name, CreatedDate from Account Where CreatedDate != null];
     Map<DateTime, Account> accMap = new Map<DateTime, Account>();
     for (Account acc : accList) {
       accMap.put(acc.CreatedDate, acc);
     }
     return accMap;
   }
}
```

**Async Apex:**

1. What is the difference between future and queueable methods? Which is more scalable and why?
2. Can we call one future method from another? Why?
3. What is the return type of a future method?
4. If we need to call an API from a future method, which annotation is required?
5. What can be done from a future method that is not possible from a queueable method? If yes, then how?
6. Can we call a batch class from a queueable class?
7. How much job chaining can we do in a queueable method?

**LWC (Lightning Web Components):**

1. What are @API, @track, and @wire in LWC?
2. What are the lifecycle hooks in LWC? Explain each.
3. Can we use @api and @track on the same variable? Why or why not?
4. How does communication happen between Parent and Child components, and vice versa?
5. How do we communicate between unrelated components?
6. I need to create an LWC component and deploy it on the Account record page. Whichever Account record page I deploy this component on, it should work dynamically. Also, when I change any data in the Account, the change should be reflected in the component without refreshing the page. How do we achieve this?
7. What are the ways to fetch data in LWC?
8. What is LDS (Lightning Data Service), and what is it used for?
9. Write an imperative method in LWC that fetches data from Apex and is called when the page is refreshed.
10. Call an Apex method imperatively and display Account data with related Contact information in the UI.
11. How can we call an external API in LWC?

**Admin:**

1. What is the security model of Salesforce?
2. What are the different ways to share records in Salesforce?
3. We have three different regions, and we need to show different fields to users from each region. How do we do this?
4. We have an action button on the Account record page. When clicked, it opens a modal with a data table showing Account data. Can you explain how this works?
5. We have a Boolean field in a custom metadata object. If this is true, then the email field on Account is mandatory. If false, the email field is optional. If true and the user doesn't provide an email, how do we show an error on the field or page?
6. We have two users with the same role and profile, but one of them is not able to see Opportunities. What could be the issue?
7. Can we restrict permissions using Permission Sets?
8. What are Remote Site Settings in Salesforce?
9. What is Named Credentials? If we set Named Credentials, do we still need to set Remote Site Settings?
10. Create a flow: When a new Account is created, increment the count by one and update the Account's description.
11. What are Custom Settings used for? What are the different types of Custom Settings?
12. What is an Account, Contact, Opportunity, and Lead in Salesforce?
13. What are the different types of relationships in Salesforce?
14. What is a Junction Object, and have you worked with one? If yes, explain it.
15. What are the different types of Flows? Which types have you worked on?
16. What does a Platform Event Trigger Flow do?
17. Explain the entire Lead process in Salesforce.
18. Explain the entire Case process in Salesforce.

**Experience Cloud:**

1. How do I publish a component on Experience Cloud?
2. I want to capture data from an LWC component that I deployed on Experience Cloud. Explain the flow for capturing and processing the data.
3. If a user is able to access and interact with my website, what settings do I need to configure?
4. What is the Guest User Profile, and how do we provide access to a Guest User for Apex classes and other resources?

**Scenario-Based Questions:**

1. If you're working as a developer and an email is fired from your org regarding a query, but the user says they didn’t receive any email, how do you handle it?
2. If your client reaches out and says, "I want this functionality," but you're not familiar with it, how do you handle the situation? What would you say to satisfy the client?
3. If you want to integrate something and there is no documentation available, what approach would you take to complete the integration?
4. If you're working on something and encountering an error, and you've tried everything else, what would you do to solve it?

