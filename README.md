# Salesforce Trigger: Update Contact When Account Name Changes

## Description

This Apex trigger updates a custom field on related `Contact` records whenever an `Account`'s `Name` field is changed. It ensures that the `Account_Name__c` field on all child Contacts reflects the latest Account name.

## Use Case

In many Salesforce implementations, business teams want visibility into the Account name directly on the Contact record for quick reference and reporting. This trigger keeps that field synchronized automatically.

---

## Trigger Details

- **Object**: Account  
- **Event**: `after update`  
- **Purpose**: Auto-update related Contacts’ `Account_Name__c` when Account Name changes  
- **Custom Field** on Contact:
  - `Account_Name__c` (Text, 255)

---

## Logic Overview

1. Loop through `Trigger.new` and compare Account names using `Trigger.oldMap`.
2. Collect IDs of Accounts where the name has changed.
3. Query all Contacts related to those Accounts.
4. Update `Account_Name__c` on each Contact.
5. Perform a single DML update.

---

## Trigger Code

> The full trigger code is available in the file:  
`UpdateContactAccountName.trigger`

---

## How to Test

1. Create an Account and a few related Contacts.
2. Change the Account name.
3. Check if the `Account_Name__c` field on the related Contacts has been updated accordingly.

---

## Skills Demonstrated

- Use of `Trigger.new` and `Trigger.oldMap`
- SOQL best practices
- DML optimization
- Trigger design and logic separation

---

## Author

**Jasvinder Singh**  
Salesforce Certified Admin & PD1 

linkedin.com/in/jasvinder-singh-kashmiri

---

## License

This project is for educational and portfolio purposes only.
