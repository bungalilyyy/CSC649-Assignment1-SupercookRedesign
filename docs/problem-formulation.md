Introduction:

Supercook is a popular cook apps recipe discovery platform designed to help users find meals based on the ingredients they currently have at home. 
By allowing users to input available items, the app generates matching recipes to maximize food utility and simplify meal planning. 
The app uses Natural Language Processing techniques by choosing specific ingredients to determine the meals based on what the user has. 
Therefore, several issues have to be solved where users may still struggle to decide how to turn leftover food into new meals. 
If this problem is not going to be solved, it can lead to food waste.

Problem Statement: 

Home cooks using recipe applications to prepare meals from available ingredients may encounter missing pantry information, disappearing saved recipes, and recommendations containing unavailable ingredients. For example, Bill S (2023) reported that ingredients entered on one computer did not appear on another computer using the same account, while DJ (2024) reported that saved recipes disappeared and the application reset when switching between apps. ReNew Innovations (2026) also reported that SuperCook suggested recipes using out-of-stock pantry items. These reported problems interrupt meal planning and make it harder for users to identify recipes they can prepare with their current ingredients. Therefore, this project proposes an NLP-assisted recipe recommendation system with ingredient-availability tracking and persistent pantry storage to address these reported difficulties. 

Users and Stakeholders 
1. Primary Users: Individuals looking to cook meals using available pantry leftovers, reduce grocery bills, and minimize household food waste
2. Secondary Users: Users who require immediate recipe discovery without forced account setup
3. Stakeholders: System developers and UI/UX designers aiming to deliver seamless data synchronization and effective recipe matching algorithms.

Project Scope 
In-Scope 
1. Implementation of an offline-first local storage system with background cloud synchronization for saved recipes and pantry lists.
2. Integration of Natural Language Processing (NLP) text processing for dynamic ingredient-recipe matching
3. Development of an ingredient availability tracking system (In-Stock / Out-of-Stock toggles)
4. Introduction of context-aware ingredient substitution suggestions when items are missing

Out-of-Scope
1. Direct API integration with commercial grocery ordering platforms (e.g., Lotus's, GrabMart). 
2. Paid subscription and payment gateway processing. 
