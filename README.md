# Grab&Go Application

## Table of Contents

- [1. Inspiration](#inspiration)
- [2. Concept](#concept)
- [3. Implementation](#implementation)
- [4. Entity Relationship Diagram (ERD)](#entity-relationship-diagram)
- [5. User Stories](#user-stories)
- [6. Use Cases](#use-cases)
- [7. Use Case Diagram](#use-case-diagram)
- [8. Requirements](#requirements)
- [9. Wire-Frames (DRAFT)](#wire-frames)
- [10. Feature List](#feature-list)

## INSPIRATION

After having a newborn this past year, I have discovered how precious and valuable all those 86,400 seconds in the day are.  This application is an attempt to gain back a few of them each week. It was thought of after many trips of going to the store trying to find the few items on my list quickly, only to find myself backtracking down aisles as if I am on a scavenger hunt. 

## CONCEPT
The Concept is simple. 
Have a list of grocery store items listed in a way that allows you to traverse a store in the most efficient/quickest manner. This way you are not going down an aisle more than once. 

## IMPLEMENTATION

To accomplish this task, a few inventories would have to be maintained:

 - List of Aisles in a particular store
 - The sections that each Aisle contains
 - A Catalog of items along with the section they belong to
 - A list of items on a users Shopping List

## ENTITY RELATIONSHIP DIAGRAM

![Grab&Go ERD](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/Grab%20and%20Go%20ERD.png)

## USER STORIES

1) As a User, I need to input Grocery Items, So that I can track what I need.

2) As a User, I need to re-order my grocery List items, So they are listed in a way relating to their location in a Grocery store.

3) As a User, I need to view a map the store aisles and my listed items, So I can have a better visual of my items and where they are in the store.

4) As a User, I need to select the store that I would like to shop at, so my list is tailored to the aisle layout of the specific store I select.

5) As a User, I need to be able to share my list with another user, so that I can coordinate my shopping efforts with another user.

6) As an Administrator, I need to add additional stores and layouts, So that my users have more options with their shopping efforts.

7) As a user, I need to indicate the items I have physically obtained when shopping, so that I can see what items are left to get on my list.

## USE CASES

1) Given the user has never logged in,
	When the user attempts to login,
	Then they are prompted to sign up via the Sign Up page

2) Given the user has created an account,
	When they have successfully logged in,
	Then their list of items will be displayed
	And they will in the order they have previously inputted the items.

3) Given that the user has one or more items in their list,
	When they select “Let’s Go Shopping” Button,
	Then their list will reorder based on the relative location in the store,
	And based on the items relative location to other items in the list.

4) Given that the user does not want to shop at the default store selected,
	When they select the Store name,
	Then the user can select a different store to shop at,
	And the ordered list will be tailored to the newly selected store.

5) Given the user has a combination of refrigerated and non-refrigerated items in their list,
When the user selects “Let’s Go Shopping” Button,
Then the ordered list will ensure refrigerated items are at the end of the list.

6) Given that the Administrator has a new Store Layout to add to the system,
When they add all of the information for the additional store,
Then the added store is available for all users to select as their store to shop from.

7) Given the user is shopping and obtained a grocery item in a store,
When they check off an item on their ordered list of grocery items,
Then the item is displayed in strike through font
And moved to the bottom of the list.

## USE CASE DIAGRAM
![Use Case Diagram](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/UML%20Use-Case%20Diagram.png)

## REQUIREMENTS

* 1.0\. User Shall Input Grocery Items into personal List by selecting items from a pre-populated list

	* 1.1\. System Shall show user categories of items or all items for user to select from

		* 1.1.1\. The software shall maintain the relationship of items and their parent category

		* 1.1.2\. The software shall allow searching an filtering of users typed values with values in the stored list of grocery items

* 2.0\. User Shall view their list in an ordered manner

	* 2.1\. The System shall compare user list with specific store layout to generate an ordered list

		* 2.1.1\. The software shall display the users list in the newly ordered format

* 3.0\. User shall select a map view of the were their items are in the store

	* 3.1\. The system shall map the location of users items onto a known store map

* 4.0\. User shall be able to create an account

	* 4.1\. The system shall store a users username and password for sign in purposes

		* 4.1.1\. The software shall validate the email is in a valid email format

		* 4.1.2\. The software shall ensure that the username is not already in the system database

		* 4.1.3\. The system shall alert the user if validation fails and gives reason why validation failed

		* 4.1.4\. The system will generate a new Shopping list record and associate the Shopping List ID with the user account

	* 4.2\. The system shall link a user account with a grocery list that the user creates

* 5.0\. User shall be able to share their list with another user

	* 5.1\. The system will ensure that another user exists

		* 5.1.1\. The software will compare requested username with list of created accounts

		* 5.1.2\. The software will notify original user of the requested user does not exists and halt shopping list linking

	* 5.2\. The system will prompt requested user upon next login that they have been selected to share list

	* 5.3\. The system will link list upon requested users acceptance

		* 5.3.1\. The software will drop the requested users shopping list table from the database

		* 5.3.2\. The software will add the Shopping List ID of the original user to the requested users account to compete the linking process

* 6.0 \. The Administrator shall add new grocery items to the Master Grocery List

	* 6.1\. The system shall display a form to the administrator for all required information of a grocery item

		* 6.1.1\. The Software shall run script(s) to take form data and create a new record of the item in the Master Grocery List Table

* 7.0\. The Administrator shall be able to add a new Store and Layout to the System

	* 7.1\. The System shall display a form to the administrator for all required information of a Store entity

		* 7.1.1\. The software shall run script(s) to take form data and create a new record of the item in the Store Table

## WIRE FRAMES

The Landing Page would be a login Screen with the Grab & Go Logo and a tab to be able to sign up:
![Landing Page](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/Landing%20Page.png)

After selecting the "Sign Up' Tab, the user can enter their information where it can be validated and submitted for account creation:
![Sign Up Screen](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/Sign%20Up%20Screen.png)

One logged in, the user can create a shopping list in an arbitrary order. This list can be shared with other users such as a family member or spouse:
![Shopping List](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/Shopping%20List.png)

Once the "Let's go shopping" being has been clicked, the app will take the users list of items and reorder them in a way that creates the "fastest path" through the store. A map view can also be shown identifying the location of the items in the store with a bird's eye view of the store:
![Store Map](https://github.com/cjpleasant88/Grab-Go/blob/master/Assets/Store%20Map.png)


## Feature List
Additional features that would be welcomed would be:

 - Ability to scan bar codes of items and add to list
 - Have different Store maps/information to choose from
 - Integration of Available coupons
 - Recipe Integration
 - Home Pantry Inventory
