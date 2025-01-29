# Revenue Recognition Assignment

## Project Description

This project implements a solution for revenue recognition in Salesforce using **Apex** and **Lightning Web Components (LWC)**. The solution calculates revenue recognition milestones for an **Opportunity** record and displays them in a **Revenue Recognition Dashboard**. The calculated milestones include both **product delivery** and **subscription-based revenue recognition**.

## Project Structure

The project contains the following key components:

### 1. **Apex Class: RevenueRecognition.cls**
   - This Apex class calculates the revenue recognition milestones based on the **Opportunity**, **OpportunityLineItem**, and **Invoice** objects.
   - The class includes logic to calculate milestones like **Product Delivery (40%)** and **Subscription-Based (60%)** over a 12-month period.

### 2. **LWC Component: RevenueRecognition**
   - A Lightning Web Component (LWC) that displays the calculated revenue recognition milestones in a table format.
   - The component fetches milestone data from the Apex service and dynamically renders it in a tabular format.
   - The table includes columns for **Milestone Name**, **Amount**, and **Recognition Date**.

### Project Folder Structure
RevenueRecognition_Project.zip
├── revenueRecognition/
│   ├── revenueRecognition.html
│   ├── revenueRecognition.js
│   ├── revenueRecognition.css
│   └── revenueRecognition.js-meta.xml
|── classes
|   ├── RevenueRecognition.cls
|


## Features

- **Milestone-Based Recognition**: The solution recognizes 40% of the revenue upon product delivery.
- **Subscription-Based Recognition**: 60% of the revenue is recognized over 12 months, starting from the Opportunity **CloseDate**.
- **LWC Display**: The component displays calculated milestones with amounts and recognition dates in a table format.
- **Integration**: The LWC component is embedded on the Opportunity record page.

## Usage

### To use the Revenue Recognition solution:
1. **Deploy the Apex Class**:
   - Deploy the `RevenueRecognition.cls` Apex class to your Salesforce org. This will handle the revenue recognition calculations.
   - The class uses `Opportunity`, `OpportunityLineItem`, and `Invoice` objects to calculate the milestones.
   
2. **Deploy the Lightning Web Component**:
   - Deploy the `RevenueRecognition` LWC to your Salesforce org.
   - This component should be added to the **Opportunity Record Page**.

3. **View Revenue Recognition Milestones**:
   - Once the LWC component is added to the Opportunity record page, users will see a table displaying the revenue recognition milestones, including:
     - **Milestone Name** (e.g., "Product Delivery", "Subscription Month 1")
     - **Amount** (calculated percentage of the total revenue)
     - **Recognition Date** (calculated based on the Opportunity Close Date and subscription periods)

## Error Handling

The solution includes error handling in the Apex class and LWC component to ensure smooth operation:

1. **Apex Class Error Handling**:
   - The Apex class handles potential issues like missing Opportunity data or invoice status.
   - If the necessary data is missing, the system will return a clear error message.

2. **LWC Error Handling**:
   - In the LWC, errors from the Apex service are captured and displayed in the component. If any issue occurs (e.g., no data returned), an error message will be shown to the user.

## Future Enhancements

- Support for additional revenue recognition logic (e.g., multi-year subscriptions, custom recognition rules).
- Integration with **Salesforce Billing** for automatic milestone generation.
- Improved UI/UX for milestone tracking and updates.

