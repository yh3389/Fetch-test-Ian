# Data Modeling for E-trade System

## Part One: Contents of Each Table

### Users Table
The Users table carries:
- A precise user identifier (`_id`)
- The nation wherein the person resides (`kingdom`)
- The date the person account became created (`createdDate`)
- The ultimate login date (`lastLogin`)
- The user position (`position`)
- The active repute of the person account (`energetic`)
- The supply through which the user signed up (`signUpSource`)

Each user should have a completely unique identifier and the relevant information noted to preserve person-unique records as it should be.

### Receipts Table
The Receipts desk consists of:
- A unique receipt identifier (`_id`)
- The quantity of bonus factors earned (`bonusPointsEarned`)
- The purpose for earning bonus points (`bonusPointsEarnedReason`)
- The date the receipt become created (`createDate`)
- The date it became scanned (`dateScanned`)
- The date the receipt processing finished (`finishedDate`)
- The date it turned into remaining changed (`modifyDate`)
- The date points have been offered (`pointsAwardedDate`)
- The number of points earned (`pointsEarned`)
- The date of buy (`purchaseDate`)
- The count of bought items (`purchasedItemCount`)
- The reputation of the receipt (`rewardsReceiptStatus`)
- The total amount spent (`totalSpent`)
- A foreign key referencing the Users table (`userId`)

Each receipt need to be related to a person and includes exact transaction information.

### Items Table
The Items table consists of:
- A precise object identifier (`_id`)
- A foreign key referencing the Receipts table (`receiptId`)
- The barcode of the item (`barcode`)
- A description of the object (`description`)
- The final charge paid (`finalPrice`)
- The item’s unique fee (`itemPrice`)
- The quantity purchased (`quantityPurchased`)
- A flag indicating if the object turned into newly flagged by the user (`userFlaggedNewItem`)
- A overseas key referencing the Brands table (`brandId`)

This table captures special information about every object purchased in a transaction and its affiliation with receipts and brands.

### Brands Table
The Brands table consists of:
- A unique logo identifier (`_id`)
- The barcode associated with the emblem (`barcode`)
- The logo code (`brandCode`)
- The class of merchandise the emblem sells (`class`)
- The class code (`categoryCode`)
- A foreign key referencing the Cogs table (`cpgId`)
- An indicator if the emblem is a pinnacle brand (`topBrand`)
- The name of the brand (`call`)

Each logo is uniquely identified and classified, ensuring organized brand-unique facts.

### Cogs Table
The Cogs table includes:
- A specific cog identifier (`_id`)
- A reference characteristic (`ref`)
- An oid characteristic (`oid`)

This table serves as a categorization or product grouping entity for brands, imparting a based way to arrange manufacturers into logical agencies.

## Part Two: Relationships

### Users and Receipts
For each consumer, the database need to hold tune in their specific person identifier, nation, account introduction date, closing login date, function, energetic status, and signal-up source. Each user ought to be related to at least one receipt, however can be related to many. Each receipt must be related to exactly one consumer.

### Receipts and Items
Each receipt must comprise a completely unique receipt identifier, details about bonus factors earned, the motive for incomes them, creation date, test date, finished date, change date, points awarded date, points earned, purchase date, bought object matter, receipt status, general quantity spent, and a person identifier referencing the Users desk. Each receipt need to comprise as a minimum one object, but can comprise many. Each object ought to be related to exactly one receipt.

### Items and Brands
Each object need to consist of a unique object identifier, receipt identifier referencing the Receipts table, barcode, description, final rate, unique charge, quantity bought, a flag indicating if it become newly flagged by way of the person, and a logo identifier referencing the Brands desk. Each item need to be associated with precisely one brand, and every brand can have multiple items associated with it.

### Brands and Cogs
Each brand should include a unique logo identifier, barcode, emblem code, class, category code, cog identifier referencing the Cogs desk, pinnacle emblem indicator, and emblem call. Each logo need to be associated with precisely one cog, and every cog will have multiple brands related to it.

### Cogs
Each cog ought to have a completely unique identifier, reference attribute, and oid characteristic. This desk enables in categorizing and organizing manufacturers into logical organizations, ensuring that every logo is part of a broader class or product organization.
