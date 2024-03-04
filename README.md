# WebTracker
This project aims to develop a comprehensive web application designed to help users manage their personal finances and health metrics effectively. 

# Project Requirements: Budget Module

## Overview
The Budget Module allows users to manage and track their expenditures by inputting items with specific attributes. It offers a detailed analysis of how each item affects the overall budget, accommodating both one-time and long-term consumptions.

## Functionalities

### Item Attributes
- **Attributes:**
  - `Total Value` (Required): Represents the overall value of the item, where income is a positive value and expense is a negative value.
  - `Start Date` (Required): The date when the transaction begins.
  - `End Date` (Optional): The date when the transaction ends. The system ensures that the `Daily Consumption Proportion` and `End Date` do not conflict. If `End Date` is not provided, the system calculates the cost up to the current date.
  - `Renewal Frequency` (Enum, Optional): Defines the renewal period for ongoing transactions (e.g., one-time, monthly, yearly).
  - `Source` (String, Optional): The origin or reason for the transaction.
  - `Daily Consumption Proportion` (Unsigned Float, Optional): A positive decimal <= 1, denoting the daily portion of the total transaction. It must align with the `End Date` if both are provided.
  - The system allows for future addition of attributes as needed.

### Budget Analysis
- Offers detailed analysis of transactions over a selected date range, including:
  - A pie chart of expenses.
  - A comparison chart of total income versus total expenses.
  - A plot showing daily income and expense trends.
- Analysis considers items with only a `Start Date` or those without an `End Date`, calculating daily costs accordingly.

### Item Management
- Enables creation and saving of new items.
- Allows use of item prototypes with default but editable attributes.
- Facilitates querying of ongoing costs (items without `End Dates`), with options to modify them based on user needs (e.g., updating the `End Date` for replaced items).

### Advanced Functionality
- The system prevents input of conflicting `Daily Consumption Proportion` and `End Date`.
- Supports specific analysis for user-selected periods, offering insights through various charts and plots based on the transaction types and their durations.
- Enables users to manage ongoing costs effectively, with flexibility to adjust for replacements or additions to their assets or expenses.

## Examples

### ChatGPT Subscription
- **Total Value:** -$33
- **Start Date:** Jan. 1st, 2024
- **End Date:** None
- **Renewal Frequency:** Monthly
- **Source:** None
- **Daily Consumption Proportion:** None

This example illustrates a monthly recurring expense for a ChatGPT subscription, starting from January 1st, 2024, without a specified end date. The subscription is marked with a monthly renewal frequency, indicating it recurs every month. The system is designed to automatically generate a new `ChatGPT Subscription` item for each subsequent month, based on the renewal frequency, and will update the `End Date` for each item appropriately to reflect the one-month usage period before the next renewal. This automation ensures continuous tracking of the subscription cost over time without manual input for each renewal period.

### K2 Paycheck
- **Total Value:** +$1000
- **Start Date:** Jan. 15th, 2024
- **End Date:** None
- **Renewal Frequency:** One-time
- **Source:** "Work"
- **Daily Consumption Proportion:** None

This example represents an income entry from employment, marked as a one-time transaction, with no specified end date, reflecting the nature of periodic income.

### Vitamin E
- **Total Value:** -$40
- **Start Date:** Jan. 10th, 2024
- **End Date:** None
- **Renewal Frequency:** One-time
- **Source:** Costco
- **Daily Consumption Proportion:** 1/500

In this example, a one-time purchase of Vitamin E supplements is logged with no specific end date. The daily consumption proportion indicates a long-term consumption plan, extending beyond a single month or payment period.

### Mouse
- **Total Value:** -$135
- **Start Date:** Jan. 10th, 2024
- **End Date:** Feb. 10th, 2024
- **Renewal Frequency:** One-time
- **Source:** Amazon
- **Daily Consumption Proportion:** None

This example details a one-time purchase of a mouse from Amazon, with a clear start and end date specified. The inclusion of an end date might indicate the user's intention to replace an old mouse with this new purchase. The system's flexibility allows users to add or modify the end date at any time, accommodating changes such as upgrades or replacements. This feature ensures that the budget tracking system remains accurate and up-to-date with the user's actual expenditures and asset replacements.

