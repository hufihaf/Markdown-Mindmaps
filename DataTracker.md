# Contract Data Tracker
## Core Tracker Notes:

6 tabs in total:  
    1. clin data tab  
	2. action plan tab  
	3. slin data tab  
	4. obligation data tab    
	5. invoice data tab  
	6. paid data tab  

Lengths of tabs:  
	1. A to AG (33 columns)  
	2. A to J (10 columns)  
	3. A to AC (29 columns)  
	4. ??? (starts with M, has 11 columns)  
	5. ??? (starts with M, has 11 columns)  
	6. ??? (starts with M, has 6 columns)  

## Table of Contents
>[Contract Number](#contract-number)  
>
>[Delivery/Task Order Number](#deliverytask-order-number)
>
>[Contractor](#contractor)
>
>[SLIN](#slin)
>
>[ACRN](#acrn)
>
>[Hours](#hours)
>
>[Cost](#cost)
>
>[Fee](#fee)
>
>[Obligation](#obligation)
>
>[Action Type](#action-type)
>
>[Funding Document](#funding-document)
>
>[Purchase Requisition](#purchase-requisistion)



## **Contract Number**
- "Unique identifier assigned to a specific contract"
    - "includes codes that identify the **agency**, the **type of contract**, the **fiscal year**, and a unique **serial number**
- Core Tracker Locations:
    - CLIN Data Tab, B
    - Action Plan Tab, B
- File Sys Location
    - RedactedFile_fY18 / RedactedFile_fY18 / N0024418D0003 / N00244-18-D-0003 P00035 Verizon / F1 - Orig K / REDACTED_F1_0003_18F0035_P00003_Original Contract.pdf

---
## **Delivery/Task Order Number**
- "Task orders are issued under an existing contract to assign specific work or deliverables as needed"
    - example = "N6339417F3006" (the "F" is the identifier I believe. Otherwise it looks just like the contract number)
- "Delivery orders are issued under an existing contract to assign specific work or deliverables as needed"

- Core Tracker Locations:
    - CLIN Data Tab, C
    - Action Plan Tab, C

- File Sys Location
    - RedactedFile_fY18 / RedactedFile_fY18 / N0024418D0003 / N00244-18-D-0003 P00035 Verizon / F1 - Orig K / REDACTED_F1_0003_18F0035_P00003_Original Contract.pdf

---
## **Contractor**
- "The main party responsible for fulfilling the contract"
    - "company name"
- Core Tracker Locations:
    - CLIN Data Tab, D
- File Sys Location
    - RedactedFile_fY18 / RedactedFile_fY18 / N0024418D0003 / N00244-18-D-0003 P00035 Verizon / F1 - Orig K / REDACTED_F1_0003_18F0035_P00003_Original Contract.pdf

---
## **SLIN**
- "Subline Item Number" ... "Provides more detail under a parent CLIN - it's funding" ... "SLINs breakdown CLINs into smaller components, such as seperate funding lines and/or tasks
    - "0001AB"
- Core Tracker Locations:
    - SLIN Data Tab, Y
- File Sys Location
    - RedactedFile_fY18 / RedactedFile_fY18 / N0024418D0003 / N00244-18-D-0003 P00035 Verizon / F1 - Orig K / REDACTED_F1_0003_18F0035_P00003_Original Contract.pdf
- PAGE 7

---
## **ACRN**
- "Accounting Classification Reference Number" ... "To track funding at a detailed level within a contract"
    - ALWAYS two characters... like "XX" or "AH"
- Core Tracker Locations:
    - SLIN Data Tab, Z
- File Sys Location
    - RedactedFile_fY18 / RedactedFile_fY18 / N0024418D0003 / N00244-18-D-0003 P00035 Verizon / F1 - Orig K / REDACTED_F1_0003_18F0035_P00003_Original Contract.pdf
- PAGE 3

---
## **Hours**
- "To define the total number of labor hours awarded"
- Core Tracker Locations:
    - CLIN Data Tab - M, R

---
## **Cost**
- "To specify the total cost value awarded, excluding fee"
- Core Tracker Locations:
    - CLIN Data Tab - N, S

---
## **Fee**
- "To provide potential fee based on hours worked or performance criteria"
- Core Tracker Locations:
    - CLIN Data Tab - O, T

---
## **Obligation**
- "Sums all the obligated quantities, hours, cost, fee and CPFF obligated entered for the CLIN from the Obligation Data tab, including only values related to Award, Incremental Funding, De-obligations, SLIN Increases and Administrative actions.
- Core Tracker Locations:
    - CLIN Data Tab - W, X, Z (???)

---
## **Action Type**
- "To clasify the nature of contract or procurement action"
- Core Tracker Locations:
    - Action Plan Tab, E
    - Obligation Data Tab, U
- Examples: "De-obligation", "Administrative Modification", "SLIN Increase", "Ceiling Adjustment"

---
## **Funding Document**
- "To provide the official details and authorization of appropriation funds" ... "Used to organize and price individual components of a contract/task order, delivery order, or purchase order"
- Core Tracker Locations:
    - SLIN Data Tab, H

---
## **Purchase Requisistion**
- "To identify a formal request to procure goods or services" ... "Generated internally before issuing a purchase order or contract/task order"
    - Example: "1300810825"
- Core Tracker Locations:
    - SLIN Data Tab, B

---